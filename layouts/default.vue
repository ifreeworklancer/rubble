<template>
    <div>

        <custom-svg/>

        <nuxt/>

    </div>
</template>

<script>
    import CustomSvg from '~/components/CustomSvg';
    const data = require('../db.json');

    export default {
        components: {
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


