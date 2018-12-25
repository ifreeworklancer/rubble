<template>
    <main>
        <intro/>
        <connection/>
        <catalog/>
        <about/>
        <technique/>
        <contacts/>
        <modal/>
    </main>
</template>

<script>
    import Intro from '~/components/Intro.vue';
    import Connection from '~/components/Сonnection.vue';
    import Catalog from '~/components/Catalog.vue';
    import About from '~/components/About.vue';
    import Technique from '~/components/Technique.vue';
    import Contacts from '~/components/Contacts.vue';
    import Modal from '~/components/Modal.vue';

    export default {
        head: {
            script: [
                {src: 'https://unpkg.com/flickity@2/dist/flickity.pkgd.min.js'},
                {src: 'https://cdnjs.cloudflare.com/ajax/libs/rellax/1.7.1/rellax.min.js'}
            ],
        },
        components: {
            Intro,
            Connection,
            Catalog,
            About,
            Technique,
            Contacts,
            Modal
        }
    }
</script>

<style>

</style>

