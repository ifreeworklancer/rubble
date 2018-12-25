<template>
    <section id="technique">
        <div class="container-fluid px-0">
            <div class="row w-100 m-0 justify-content-center">
                <div class="col-12 px-3">
                    <h2 class="section-title text-dark text-center">
                        {{technique.title}}
                    </h2>
                </div>
                <div class="col-sm-6 col-lg-3 px-0" v-for="image in technique.images" :key="image">
                    <div class="technique-img" :style="{ backgroundImage: 'url(' + image + ')' }"></div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>


    export default {
        data() {
            return {
                technique: require('../db').technique
            }
        }
    }


</script>

<style lang="scss" scoped>
    @import "../assets/app.scss";

    #technique {
        padding-top: 70px;

        .section-title {
            margin-bottom: 40px;
        }
    }

    .technique-img {
        width: 100%;
        height: 200px;
        @extend %img;

        @media (min-width: map_get($grid-breakpoints, sm)) {
            height: 250px;
        }

        @media (min-width: map_get($grid-breakpoints, xl)) {
            height: 300px;
        }
    }
</style>

