<template>
<div>
    <h4 class="section-title p-l-10">Subscriptions</h4>
    <div class="card subscriptions">
        <div class="card-block">
            <div id="generic_price_table">
                <div class="d-flex" >
                    <div class="generic_content active clearfix">

                        <div class="generic_head_price clearfix">

                            <div class="generic_head_content clearfix">

                                <!--HEAD START-->
                                <div class="head_bg"/>
                                <div class="head">
                                    <span>Plan 1</span>
                                </div>
                                <!--//HEAD END-->

                            </div>
                            <div class="generic_price_tag clearfix">
                                <span class="price">
                                    <span class="sign">$</span>
                                    <span class="currency">100</span>
                                    <span class="cent">.00</span>
                                    <span class="month">/month</span>
                                </span>
                            </div>

                        </div>
                        <div class="generic_feature_list">
                            <ul>
                                <li>
                                    <span> 10</span> accounts
                                </li>
                                <li>
                                    <span> 10</span> accounts
                                </li>
                                <li>
                                    <span> 10</span> accounts
                                </li>
                            </ul>
                        </div>
                        <div class="generic_price_btn clearfix">
                            <a href="#">Try</a>
                        </div>
                    </div>
                    <div class="generic_content active clearfix">

                        <div class="generic_head_price clearfix">

                            <div class="generic_head_content clearfix">

                                <!--HEAD START-->
                                <div class="head_bg"/>
                                <div class="head">
                                    <span>Plan 2</span>
                                </div>
                                <!--//HEAD END-->

                            </div>
                            <div class="generic_price_tag clearfix">
                                <span class="price">
                                    <span class="sign">$</span>
                                    <span class="currency">50</span>
                                    <span class="cent">.00</span>
                                    <span class="month">/month</span>
                                </span>
                            </div>

                        </div>
                        <div class="generic_feature_list">
                            <ul>
                                <li>
                                    <span> 5</span> accounts
                                </li>
                                <li>
                                    <span> 5</span> accounts
                                </li>
                                <li>
                                    <span> 5</span> accounts
                                </li>
                            </ul>
                        </div>
                        <div class="generic_price_btn clearfix">
                            <a href="#">Try</a>
                        </div>
                    </div>
                    <div class="generic_content active clearfix">

                        <div class="generic_head_price clearfix">

                            <div class="generic_head_content clearfix">

                                <!--HEAD START-->
                                <div class="head_bg"/>
                                <div class="head editing">
                                    <input type="text" placeholder="Plan name" class="form-control">
                                </div>
                                <!--//HEAD END-->

                            </div>
                            <div class="generic_price_tag clearfix">
                                <span class="price editing">
                                    <span class="sign">
                                        <multiselect
                                            :options="[ '$', '€' ]"
                                            :show-labels="false"
                                            :allow-empty="false"
                                            placeholder="Sign"
                                            :searchable="false"
                                        />
                                    </span>
                                    <span class="currency">
                                        <input type="text" placeholder="Price" class="form-control">
                                    </span>
                                    <span class="cent"></span>
                                    <span class="month">
                                        <multiselect
                                            :options="[ 'Monthly', 'Anually' ]"
                                            :show-labels="false"
                                            :allow-empty="false"
                                            placeholder="Recurrency"
                                            :searchable="false"
                                        />
                                    </span>
                                </span>
                            </div>

                        </div>
                        <div class="generic_feature_list editing">
                            <ul>
                                <li>
                                    <input type="text" placeholder="Feature" class="form-control" value="2 accoounts">
                                </li>
                                <li>
                                    <input type="text" placeholder="Feature" class="form-control" value="2 accoounts">
                                </li>
                                <li>
                                    <input type="text" placeholder="Feature" class="form-control">
                                </li>
                            </ul>
                        </div>
                        <div class="add-feature">
                            <i class="fas fa-plus"></i>
                            add feature
                        </div>
                    </div>
                    <div class="add-plan">
                        <i class="fas fa-plus"></i>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>
