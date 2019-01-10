<template>
    <div>
        <h4 class="section-title p-l-10">System modules</h4>
        <div class="card">
            <div class="card-block">
                <div class="w-100 text-right p-t-20 p-r-20">
                    <button class="btn btn-primary">Add module</button>
                </div>
                <div class="system-modules">
                    <div class="system-module">
                        <i class="fas fa-grip-lines row-drag"/>
                        <div>
                            <div class="system-module__title">Products <span>(products)</span></div>
                            <div class="system-module__description">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.</div>
                        </div>
                        <toggle-button />
                    </div>
                    <div class="system-module sub-module">
                        <i class="fas fa-grip-lines row-drag"/>
                        <div>
                            <div class="system-module__title">Sub module <span>(submodule)</span></div>
                            <div class="system-module__description">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.</div>
                        </div>
                        <toggle-button />
                    </div>
                    <div class="system-module sub-module">
                        <i class="fas fa-grip-lines row-drag"/>
                        <div>
                            <div class="system-module__title">Sub module <span>(submodule)</span></div>
                            <div class="system-module__description">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.</div>
                        </div>
                        <toggle-button />
                    </div>
                    <div class="system-module sub-module">
                        <i class="fas fa-grip-lines row-drag"/>
                        <div>
                            <div class="system-module__title">Sub module <span>(submodule)</span></div>
                            <div class="system-module__description">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.</div>
                        </div>
                        <toggle-button />
                    </div>
                    <div class="system-module">
                        <i class="fas fa-grip-lines row-drag"/>
                        <div>
                            <div class="system-module__title">Products <span>(products)</span></div>
                            <div class="system-module__description">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.</div>
                        </div>
                        <toggle-button />
                    </div>
                    <div class="system-module">
                        <i class="fas fa-grip-lines row-drag"/>
                        <div>
                            <div class="system-module__title">Products <span>(products)</span></div>
                            <div class="system-module__description">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.</div>
                        </div>
                        <toggle-button />
                    </div>
                    <div class="system-module">
                        <i class="fas fa-grip-lines row-drag"/>
                        <div>
                            <div class="system-module__title">Products <span>(products)</span></div>
                            <div class="system-module__description">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.</div>
                        </div>
                        <toggle-button />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.system-modules {
    padding: 20px;

    .system-module {
        display: flex;
        align-items: center;
        border-bottom: 1px solid rgba(0,0,0,.125);
        padding: 15px 0;
        cursor: pointer;

        .row-drag {
            padding-right: 15px;
            opacity: 0.4;
            cursor: all-scroll;
        }

        &__title {
            font-size: 18px;
            font-weight: 500;
            color: #317ae2;

            span {
                opacity: 0.7;
                font-size: 14px;
            }
        }

        .vue-js-switch {
            margin-bottom: 0;
            margin-left: auto;
        }

        &:first-child {
            border-top: 1px solid rgba(0,0,0,.125);
        }

        &.sub-module {
            padding-left: 50px;
        }
    }
}
</style>
