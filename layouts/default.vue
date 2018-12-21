<template>
    <div>

        <custom-svg></custom-svg>

        <!-- Header -->
        <app-header/>

        <!-- Main -->
        <nuxt/>

        <!-- Footer -->
        <app-footer/>

    </div>
</template>

<script>
    import CustomSvg from '~/components/CustomSvg';
    import AppHeader from '~/components/AppHeader';
    import AppFooter from '~/components/AppFooter';
    const data = require('../db.json');

    export default {
        components: {
            AppHeader,
            AppFooter,
            CustomSvg
        },
        data() {
            return {
                data: data
            }
        }
    }
</script>

<style lang="scss">
    @import "../assets/app";
</style>


