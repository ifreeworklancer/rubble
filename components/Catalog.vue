<template>
    <section id="catalog">
        <div class="container-fluid px-0">
            <div class="row w-100 m-0">
                <div class="col-sm-6 px-0" v-for="(value, key, index) in catalog.list" :key="index">
                    <div :class="'catalog-card catalog-card--' + value.class">
                        <div class="prev">
                            <div class="img" :style="{ backgroundImage: 'url(' + value.image + ')' }"></div>
                        </div>
                        <div class="content">
                            <h3 class="title">
                                {{value.title}}
                            </h3>
                            <a href="#" @click.prevent="open" class="btn btn-dark" :data-title="value.title">Заказать</a>
                        </div>
                    </div>
                </div>
                <div class="col-sm-6 px-0">
                    <div class="catalog-card catalog-card--delivery">
                        <div class="content order-2 order-xl-1">
                            <h2 class="title">
                                {{catalog.delivery.title}}
                            </h2>
                            <div class="subtitle">
                                {{catalog.delivery.subtitle}}
                            </div>
                            <a href="#" @click.prevent="open" class="btn btn-outline-primary">
                                Узнать больше
                            </a>
                        </div>
                        <div class="prev order-1 order-xl-2">
                            <div class="img" :style="{ backgroundImage: 'url(' + catalog.delivery.image + ')' }"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="parallax-item parallax-item-1" data-rellax-speed="2">
            <img src="images/content/parallax/parallax-3.png" alt="parallax">
        </div>

        <div class="parallax-item parallax-item-2" data-rellax-speed="2">
            <img src="images/content/parallax/parallax-4.png" alt="parallax">
        </div>

        <div class="parallax-item parallax-item-3 d-none d-xl-block" data-rellax-speed="3">
            <img src="images/content/parallax/parallax-5.png" alt="parallax">
        </div>
    </section>
</template>

<script>


    export default {
        data() {
            return {
                catalog: require('../db').catalog
            }
        },
        methods: {
            open() {
                this.$emit('open');
            }
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

    #catalog {
        overflow: visible;
    }

    .catalog-card {
        position: relative;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        padding: 40px 30px;
        height: 100%;

        @media (min-width: map_get($grid-breakpoints, xl)) {
            flex-direction: row;
        }

        @media (min-width: 1600px) {
            padding: 70px 100px;
        }

        .prev {
            width: 100%;

            @media (min-width: map_get($grid-breakpoints, xl)) {
                width: 70%;
            }

            .img {
                width: 100%;
                max-width: 500px;
                height: 250px;
                @extend %img;
                background-size: contain;

                @media (min-width: map_get($grid-breakpoints, xl)) {
                    height: 300px;
                }

            }
        }

        .content {
            width: 100%;

            @media (min-width: map_get($grid-breakpoints, xl)) {
                width: 30%;
                text-align: right;
            }

            .title {
                color: $dark;
                line-height: 1.6;
                margin-bottom: 20px;
            }
        }

        &:hover {

            &::before {
                width: 100%;
            }
        }

        &::before {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 0;
            height: 7px;
            background: $primary;
            transition: 1s;
        }

        &--light {
            background: #fff;
        }

        &--dark {
            background: #f5f5f5;
        }

        &--delivery {
            background: url("/images/content/catalog/delivery-bg.jpg") 50% 50% /cover no-repeat;

            .content {
                width: 100%;
                text-align: left;

                @media (min-width: map_get($grid-breakpoints, xl)) {
                    width: 60%;
                }

                .title {
                    color: #fff;
                    line-height: $line-height-base;
                }

                .subtitle {
                    color: #d0d0d0;
                    margin-bottom: 20px;
                }
            }

            .prev {
                width: 100%;

                @media (min-width: map_get($grid-breakpoints, xl)) {
                    width: 40%;
                }

                .img {
                    height: 150px;

                    @media (min-width: map_get($grid-breakpoints, xl)) {
                        height: 300px;
                    }
                }
            }
        }
    }

    .parallax-item {
        position: absolute;
        display: none;

        @media (min-width: map_get($grid-breakpoints, lg)) {
            display: block;
        }

        img {
            width: auto;
        }

        &-1 {
            top: -60px;
            left: 0;
        }

        &-2 {
            top: -80px;
            right: 5%;
        }

        &-3 {
            top: 180px;
            right: 0;
        }
    }

</style>

