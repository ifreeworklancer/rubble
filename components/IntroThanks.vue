<template>
    <section id="intro-thanks">
        <div class="container h-100">
            <div class="row h-100">
                <div class="col-12 h-100 d-flex justify-content-center align-items-center">
                    <div class="intro-thanks-item text-center">
                        <h1 class="title mb-0">
                            Спасибо!
                        </h1>
                        <div class="subtitle mt-3 mb-4">
                            Наш менеджер с Вами свяжется...
                        </div>
                        <nuxt-link to="/" class="btn btn-primary">
                            На главную
                        </nuxt-link>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        //
    }
</script>

<style lang="scss">
    @import "../assets/app.scss";

    #intro-thanks {
        height: 100vh;
        min-height: 600px;
        background: $secondary;
    }
</style>