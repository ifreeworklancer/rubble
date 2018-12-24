<template>
    <section id="connection">
        <div class="container">
            <div class="row justify-content-center justify-content-lg-around align-items-center">
                <div class="col-lg-5">
                    <div class="connection-item">
                        <div class="img d-none d-sm-block mx-auto mb-5 mb-lg-0" :style="{ backgroundImage: 'url(' + connection.image + ')' }"></div>
                    </div>
                </div>
                <div class="col-sm-7 col-lg-5 col-xl-4">
                    <div class="connection-item">
                        <h1 class="connection-item__title mb-0">
                            {{connection.title}}
                        </h1>
                        <div class="connection-item__subtitle">
                            {{connection.subtitle}}
                        </div>
                        <form v-on:submit.prevent="onSubmit">
                            <div class="form-column">
                                <div class="form-group">
                                    <label class="label-placeholder" for="user-name">Ваше имя</label>
                                    <input @blur="onBlur" @focus="onFocus" type="text" class="form-control" id="user-name">
                                </div>
                                <div class="form-group">
                                    <label class="label-placeholder" for="user-phone">Номер телефона</label>
                                    <input @blur="onBlur" @focus="onFocus" type="tel" class="form-control" id="user-phone">
                                </div>
                                <div class="form-group">
                                    <label class="label-placeholder" for="user-email">Email</label>
                                    <input @blur="onBlur" @focus="onFocus" type="email" class="form-control" id="user-email">
                                </div>
                                <button type="submit" class="btn btn-outline-primary">Отправить</button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
        <div class="parallax-item parallax-item-1" data-rellax-speed="7" data-paroller-type="foreground"
             data-paroller-direction="vertical">
            <img src="images/content/parallax/parallax-1.png" alt="parallax">
        </div>

        <div class="parallax-item parallax-item-2" data-rellax-speed="7" data-paroller-type="foreground"
             data-paroller-direction="vertical">
            <img src="images/content/parallax/parallax-2.png" alt="parallax">
        </div>

        <div class="parallax-item parallax-item-3" data-rellax-speed="7" data-paroller-type="foreground"
             data-paroller-direction="vertical">
            <img src="images/content/parallax/parallax-3.png" alt="parallax">
        </div>
    </section>
</template>

<script>

    // var rellax = new Rellax('.parallax-item');

    export default {
        data() {
            return {
                connection: require('../db').connection
            }
        },
        methods: {
            onBlur: function (e) {
                if(e.target.value !== "") {
                    e.target.parentNode.classList.add('in-focus');
                } else {
                    e.target.parentNode.classList.remove('in-focus');
                }
            },
            onFocus: function (e) {
                e.target.parentNode.classList.add('in-focus');
            }
        }
    }


</script>

<style lang="scss" scoped>
    @import "../assets/app.scss";

    #connection {
        padding: 95px 0;
        background: url("/images/bg/connection-bg.jpg") 50% 50% /cover no-repeat;
    }

    .connection-item {

        .img {
            width: 410px;
            height: 260px;
            margin: 0 auto;
            @extend %img;
        }

        &__subtitle {
            margin: 20px 0 40px;
        }
    }

    .form-group {
        position: relative;

        &.in-focus {

            .label-placeholder {
                left: 0;
                bottom: 100%;
                color: #888888;
            }

            .form-control {
                background: #fff;
            }
        }

        .label-placeholder {
            position: absolute;
            left: 15px;
            bottom: 0;
            transition: .5s;
        }

        .form-control {
            padding: 10px 15px;
            background: $secondary;
            border-radius: 4px;
            border: none;
            color: $dark;
            transition: .5s;
        }
    }

    .form-column {

        .form-group {
            width: 100%;
            margin-bottom: 30px;
        }

        &--min {
            max-width: 315px;
        }
    }

    .parallax-item {
        position: absolute;

        img {
            width: auto;
        }

        &-1 {
            top: 0;
            left: 5%;
        }

        &-2 {
            top: 0;
            right: 5%;
        }

        &-3 {
            bottom: 0;
            right: 10%;
        }
    }
</style>

