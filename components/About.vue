<template>
    <section id="about">
        <div class="container">
            <div class="row">
                <div class="col-sm-10 col-lg-9 col-xl-8 mx-auto">
                    <div class="about-item">
                        <h2 class="title mb-3">
                            {{about.title}}
                        </h2>
                        <div class="text" v-html="about.text"></div>
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
                about: require('../db').about
            }
        }
    }


</script>

<style lang="scss" scoped>
    @import "../assets/app.scss";

    #about {
        padding: 90px 0;
        background: url("/images/bg/about-bg.jpg") 50% 50% /cover no-repeat;
    }

    .about-item {

        .text {

            p {
                margin-bottom: 30px;
                color: #ededed;
            }
        }
    }

</style>

