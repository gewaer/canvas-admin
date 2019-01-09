<template>
<div>
    <h4 class="section-title p-l-10">General setup</h4>
    <div class="card general-setup">
        <div class="card-block">
            <form class="form-horizontal" role="form" autocomplete="off">
                <div class="form-group row">
                    <label for="fname" class="col-md-3">Lipsum</label>
                    <div class="col-md-9">
                        <input type="text" class="form-control" id="fname" name="name" required>
                    </div>
                </div>
                <div class="form-group row">
                    <label class="col-md-3">Lipsum</label>
                    <div class="col-md-9">
                        <div class="radio radio-success">
                        <input type="radio" value="male" name="optionyes" id="male">
                        <label for="male">Lorem</label>
                        <input type="radio" checked="checked" value="female" name="optionyes" id="female">
                        <label for="female">Lorem</label>
                        </div>
                    </div>
                </div>
                <div class="form-group row">
                    <label class="col-md-3">Lipsum</label>
                    <div class="col-md-9">
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry.</p>
                        <p class="hint-text small">Lorem Ipsum is simply dummy text of the printing and typesetting industry.</p>
                        <div class="row">
                        <div class="col-md-5">
                            <input type="text" class="form-control" required>
                        </div>
                        <div class="col-md-5 sm-m-t-10">
                            <input type="text" class="form-control">
                        </div>
                        </div>
                    </div>
                </div>
                <div class="form-group row">
                    <label for="position" class="col-md-3">Lipsum</label>
                    <div class="col-md-9">
                        <input type="text" class="form-control" id="position" required>
                    </div>
                </div>
                <div class="form-group row">
                    <label for="name" class="col-md-3">Lipsum</label>
                    <div class="col-md-9">
                        <textarea class="form-control" id="name"></textarea>
                    </div>
                </div>
                <br>
                <div class="row">
                    <div class="col-md-3">
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry.</p>
                    </div>
                </div>
            </form>
        </div>
    </div>
</div>
</template>
