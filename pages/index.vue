<template>
    <main>
        <intro></intro>
        <connection></connection>
    </main>
</template>

<script>
    import Intro from '~/components/Intro.vue';
    import Connection from '~/components/Сonnection.vue';

    export default {
        head: {
            script: [
                {src: 'https://unpkg.com/flickity@2/dist/flickity.pkgd.min.js'},
            ],
        },
        components: {
            Intro,
            Connection
        }
    }
</script>

<style>

</style>

