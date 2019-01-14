<template>
    <app-container>
        <h4 class="section-title p-l-10">Companies</h4>
        <div class="card">
            <div class="card-block">
                <div class="browse-filters">
                    <div class="dropdown bulk-actions">
                        <button
                            id="bulk-actions"
                            class="btn btn-info dropdown-toggle"
                            type="button"
                            data-toggle="dropdown"
                            aria-haspopup="true"
                            aria-expanded="false">
                            Bulk actions
                        </button>
                        <div class="dropdown-menu" aria-labelledby="bulk-actions">
                            <a class="dropdown-item" href="#">Action</a>
                            <a class="dropdown-item" href="#">Another action</a>
                            <a class="dropdown-item" href="#">Something else here</a>
                        </div>
                    </div>
                    <div class="input-group search-bar">
                        <input type="text" class="form-control">
                        <div class="input-group-append">
                            <button class="btn btn-primary">
                                <i class="fa fa-search"/> Search
                            </button>
                        </div>
                    </div>
                    <div class="browse-list-filters d-flex align-items-center">
                        <span class="mr-3">Filters</span>
                        <!-- <select id="multi" class="full-width" data-init-plugin="select2" multiple>
                            <option value="1">Filter 1</option>
                            <option value="2">Filter 2</option>
                            <option value="3">Filter 3</option>
                            <option class="add-custom-filter" @click.stop="addCustomFilter">Add custom filter</option>
                        </select> -->
                        <multiselect
                            v-model="currentFilters"
                            :multiple="true"
                            :show-labels="false"
                            :options="['Filter 1', 'Filter 2', 'Fiilter 3']"
                        >
                            <template slot="afterList" >
                                <div class="add-custom-filter-btn option__desc"><a class="option__title" @click="showAddCustomFilter">
                                <i class="fa fa-plus"/> Add custom Filter</a>
                                </div>
                            </template>
                        </multiselect>
                    </div>
                </div>
            </div>
        </div>
        <div class="card companies-list">
            <div class="card-block">
                <div class="row">
                    <div class="col">
                        <div class="table-responsive">
                            <vuetable
                                ref="Vuetable"
                                :append-params="appendParams"
                                :fields="companiesFields"
                                :http-fetch="getTableData"
                                api-url="/companies"
                                class="table table-hover table-condensed p-t-0"
                                pagination-path=""
                            >
                                <img
                                    slot="profile_image"
                                    slot-scope="props"
                                    :src="props.rowData.profile_image || defaultImage"
                                    height="25px"
                                >
                                <template slot="actions" slot-scope="props">
                                    <button class="btn btn-primary m-l-5" @click="editCompany(props.rowData.id, false)"><i class="fa fa-eye" aria-hidden="true"/></button>
                                    <button class="btn btn-complete m-l-5" @click="editCompany(props.rowData.id)"><i class="fa fa-edit" aria-hidden="true"/></button>
                                    <button
                                        :disabled="isCurrentCompany(props.rowData.id)"
                                        class="btn btn-danger m-l-5"
                                        @click="beforeDeleteCompany(props.rowData)">
                                        <i class="fa fa-trash" aria-hidden="true" />
                                    </button>
                                </template>
                            </vuetable>
                        </div>
                    </div>

                    <modal
                        :draggable="true"
                        :adaptive="true"
                        :scrollable="true"
                        name="company-modal"
                        height="auto"
                        @closed="selectedCompany = null"
                    />
                </div>
            </div>
        </div>
    </app-container>
</template>

<script>
import {mapState} from "vuex";

export default {
    name: "Companies",
    components: {
        AppContainer: () => import(/* webpackChunkName: "admin-app-container" */ "@v/app-details/index")
    },
    data() {
        return {
            companiesFields: [{
                name: "profile_image",
                title: "Logo",
                width: "30%"
            }, {
                name: "name",
                sortField: "name",
                width: "30%"
            }, {
                name: "actions",
                title: "Actions"
            }],
            appendParams:{
                format: "true",
                relationships: "hasActivities",
                q: "(is_deleted:0)"
            },
            defaultImage: "https://mctekk.com/images/logo-o.svg",
            isEditable: true,
            isLoading: false,
            selectedCompany: null
        }
    },
    computed: {
        ...mapState("Company", {
            company: state => state.data
        })
    },
    methods: {
        beforeDeleteCompany(company){
            if (this.isLoading) {
                return ;
            }
            if(company.hasActivities == "1"){
                this.$notify({
                    title: "Error",
                    text: "No puede eliminar esta compañia por que tiene actividades",
                    type: "error"
                });
                return ;
            }
            this.confirmDeleteCompany(company);
        },
        confirmDeleteCompany(company){
            this.$modal.show("basic-modal", {
                title:"Delete Company",
                message:`Did you want to delete ${company.name} company ?`,
                buttons: [{
                    title: "Accept",
                    class: "btn-success",
                    handler: () => {
                        this.$modal.hide("basic-modal");
                        this.deleteCompany(company.id);
                    }
                }, {
                    title: "Cancel",
                    class: "btn-danger",
                    handler: () => {
                        this.$modal.hide("basic-modal");
                    }
                }]
            });
        },
        deleteCompany(companyId) {
            this.isLoading = true;

            axios({
                url: `/companies/${companyId}`,
                method: "DELETE"
            }).then(() => {
                this.$notify({
                    title: "Deleted",
                    text: "The company has been deleted",
                    type: "success"
                });
                this.$refs.Vuetable.reload();
            }).catch((error) => {
                this.$notify({
                    title: "Error",
                    text: error.response.data.errors.message,
                    type: "error"
                });
            }).finally(() => {
                this.isLoading = false;
            })
        },
        editCompany(companyId, isEditable = true) {
            this.isEditable = isEditable;
            this.$router.push({
                name: "adminAppCompaniesEdit"
            });
        },
        getTableData(apiUrl, options) {
            return axios({
                url: apiUrl,
                params: options.params
            });
        },
        isCurrentCompany(companyId) {
            return this.company.id == companyId;
        }
    }
};
</script>
