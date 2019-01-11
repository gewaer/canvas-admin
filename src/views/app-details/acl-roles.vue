<template>
    <app-container>
        <h4 class="section-title p-l-10">ACL Roles list</h4>
        <div class="card acl-roles">
            <div class="card-block">
                <div class="row">
                    <div class="col-12 col-md-3">
                        <div class="roles__title">Roles</div>
                        <ul class="roles__list">
                            <li>
                                <a href="#">Admins</a>
                            </li>
                            <li>
                                <a href="#">Users</a>
                            </li>
                            <li class="selected">
                                <a href="#">Agents</a>
                                <div class="dropdown">
                                    <i
                                        id="dropdownMenuButton"
                                        class="fas fa-ellipsis-h dropdown-toggle"
                                        data-toggle="dropdown"
                                        aria-haspopup="true"
                                        aria-expanded="false"/>
                                    <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                                        <a class="dropdown-item" href="#">
                                            <i class="fas fa-pencil-alt"/> Rename
                                        </a>
                                        <a class="dropdown-item" href="#">
                                            <i class="fas fa-trash-alt"/> Delete
                                        </a>
                                    </div>
                                </div>
                            </li>
                            <li class="add-role">
                                <a href="#">
                                    <i class="fas fa-plus"/> Add role
                                </a>
                            </li>
                        </ul>
                    </div>
                    <div class="col-12 col-md-9">
                        <div class="permissions__title">Permissions</div>
                        <div class="permissions__list row">
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonFalse" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonTrue" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonFalse" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonTrue" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonFalse" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonTrue" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonFalse" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonTrue" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonFalse" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonTrue" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonFalse" /> Lorem ipsun dolor sit amet
                            </div>
                            <div class="col-12 col-lg-4">
                                <toggle-button v-model="toggleButtonTrue" /> Lorem ipsun dolor sit amet
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </app-container>
</template>

<script>
export default {
    name: "Roles",
    components: {
        AppContainer: () => import(/* webpackChunkName: "admin-app-container" */ "@v/app-details/index")
    },
    data() {
        return {
            toggleButtonFalse: false,
            toggleButtonTrue: true
        };
    }
}
</script>


<style lang="scss" scoped>
.acl-roles {
    padding: 20px;

    .roles__title, .permissions__title {
        font-size: 18px;
        font-weight: 500;
        border-bottom: 1px solid rgba(0,0,0,.125);
        margin-bottom: 10px;
    }

    .roles__list, .permissions__list {
        padding-left: 0;
        margin-bottom: 0;
        list-style: none;
    }

    .roles__list {
        li {
            font-size: 15px;
            padding: 5px 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: space-between;

            a {
                color: #317ae2;
            }

            i:after {
                display: none;
            }

            &.selected {
                background-color: #e6e6e6;

                a, i {
                    color: black;
                }
            }

            &:hover {
                background-color: var(--base-color);

                > a, .dropdown-toggle {
                    color: white;
                }
            }
        }

        .add-role {
            border-top: 1px solid rgba(0,0,0,.125);
            margin-top: 20px;
        }
    }

    .permissions__list {
        li {
            display: flex;
            align-items: center;
            padding: 5px 0;

            .vue-js-switch {
                margin-bottom: 0;
                margin-right: 5px;
            }
        }
    }
}
</style>
