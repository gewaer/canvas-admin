<template>
    <div class="app-details">
        <h4 class="section-title p-l-10">App details</h4>
        <div class="card">
            <div class="card-block">
                <div class="row app-details__general-information">
                    <div class="col-12 col-md-auto app-logo">
                        <img src="https://mctekk.com/images/logo-o.svg">
                    </div>
                    <div class="col-12 col-md grid-container">
                        <div class="grid-item">
                            <div class="title">App creation</div>
                            <div class="fact">12/12/2012</div>
                        </div>
                        <div class="grid-item">
                            <div class="title">Active Users</div>
                            <div class="fact">4</div>
                        </div>
                        <div class="grid-item">
                            <div class="title">Companies</div>
                            <div class="fact">8</div>
                        </div>
                        <div class="grid-item">
                            <div class="title">App creation</div>
                            <div class="fact">12/12/2012</div>
                        </div>
                        <div class="grid-item">
                            <div class="title">Active Users</div>
                            <div class="fact">4</div>
                        </div>
                        <div class="grid-item">
                            <div class="title">Companies</div>
                            <div class="fact">8</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <h4 class="section-title p-l-10">General setup</h4>
        <div class="card">
            <div class="card-block"/>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.app-details {
    &__general-information {
    padding: 20px;

        .app-logo {
            display: flex;
            align-items: center;
            justify-content: center;

            img {
                width: 200px;
            }
        }

        .grid-container {
            padding: 0%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            grid-gap: 15px;
            gap: 15px;

            .grid-item {
                display: flex;
                align-items: center;
                flex-direction: column;
                justify-content: center;

                .title {
                    font-size: 18px;
                    line-height: 25px;
                }

                .fact {
                    font-size: 24px;
                    color: var(--base-color);
                    line-height: 26px;
                }
            }
        }
    }
}
</style>
