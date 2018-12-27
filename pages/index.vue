<template>
    <div>
        <app-header @open="showModal"/>
        <main>
            <intro @open="showModal"/>
            <connection/>
            <catalog @open="showModal"/>
            <about/>
            <technique/>
            <contacts @open="showModal"/>
        </main>
        <modal v-show="isModalVisible" @close="closeModal"></modal>
        <app-footer/>
    </div>
</template>

<script>
    import AppHeader from '~/components/AppHeader';
    import Intro from '~/components/Intro.vue';
    import Connection from '~/components/Сonnection.vue';
    import Catalog from '~/components/Catalog.vue';
    import About from '~/components/About.vue';
    import Technique from '~/components/Technique.vue';
    import Contacts from '~/components/Contacts.vue';
    import Modal from '~/components/Modal.vue';
    import AppFooter from '~/components/AppFooter';

    export default {
        data() {
            return {
                isModalVisible: false
            }
        },
        components: {
            AppHeader,
            Intro,
            Connection,
            Catalog,
            About,
            Technique,
            Contacts,
            AppFooter,
            Modal
        },
        methods: {
            showModal() {
                this.isModalVisible = true;
            },
            closeModal() {
                this.isModalVisible = false;
            }
        }
    }
</script>

<style>

</style>

