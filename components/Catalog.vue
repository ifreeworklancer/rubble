<template>
    <section id="catalog">
        <div class="container-fluid px-0">
            <div class="row">
                <div class="col-sm-6 px-0" v-for="(value, key, index) in catalog.list" :key="index">
                    <div :class="'catalog-card catalog-card--' + value.class">
                        <div class="prev">
                            <div class="img" :style="{ backgroundImage: 'url(' + value.image + ')' }"></div>
                        </div>
                        <div class="content">
                            <h3 class="title">
                                {{value.title}}
                            </h3>
                            <a href="#" class="btn btn-dark" :data-title="value.title">Заказать</a>
                        </div>
                    </div>
                </div>
                <div class="col-lg-6 px-0">
                    <div class="catalog-card catalog-card--delivery">
                        <div class="content">
                            <h2 class="title">
                                {{catalog.delivery.title}}
                            </h2>
                            <div class="subtitle">
                                {{catalog.delivery.subtitle}}
                            </div>
                            <a href="#" class="btn btn-outline-primary">
                                Узнать больше
                            </a>
                        </div>
                        <div class="prev">
                            <div class="img" :style="{ backgroundImage: 'url(' + catalog.delivery.image + ')' }"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>


    export default {
        data() {
            return {
                catalog: require('../db').catalog
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
        justify-content: space-between;
        align-items: center;
        padding: 70px 100px;

        .prev {
            width: 70%;

            .img {
                width: 100%;
                max-width: 500px;
                height: 300px;
                @extend %img;
                background-size: contain;
            }
        }

        .content {
            width: 30%;
            text-align: right;

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
                width: 60%;
                text-align: left;
                
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
                width: 40%;
            }
        }
    }

</style>

