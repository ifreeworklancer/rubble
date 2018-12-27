<template>
    <section id="connection">
        <div class="container">
            <div class="row justify-content-center justify-content-lg-around align-items-center">
                <div class="col-lg-5">
                    <div class="connection-item">
                        <div class="img d-none d-sm-block mx-auto mb-5 mb-lg-0"
                             :style="{ backgroundImage: 'url(' + connection.image + ')' }"></div>
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
                        <form-column></form-column>
                    </div>
                </div>
            </div>
        </div>
        <div class="parallax-item parallax-item-1" data-rellax-speed="2">
            <img src="images/content/parallax/parallax-1.png" alt="parallax">
        </div>

        <div class="parallax-item parallax-item-2" data-rellax-speed="1">
            <img src="images/content/parallax/parallax-2.png" alt="parallax">
        </div>
    </section>
</template>

<script>

    import FormColumn from '~/components/FormColumn.vue';

    export default {
        data() {
            return {
                connection: require('../db').connection
            }
        },
        components: {
            FormColumn
        },
        mounted() {
            if (process.client) {
                var rellax = new Rellax('.parallax-item');
            }
        }
    }


</script>

<style lang="scss" scoped>
    @import "../assets/app.scss";

    #connection {
        padding: 95px 0;
        background: url("/images/bg/connection-bg.jpg") 50% 50% /cover no-repeat;
        overflow: visible;
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

    .parallax-item {
        position: absolute;
        display: none;

        @media (min-width: map_get($grid-breakpoints, sm)) {
            display: block;
        }

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
    }
</style>

