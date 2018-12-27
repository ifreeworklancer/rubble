<template>
    <div>
        <app-header-secondary/>
        <main>
            <intro-thanks/>
        </main>
    </div>
</template>

<script>
    import AppHeaderSecondary from '~/components/AppHeaderSecondary.vue';
    import IntroThanks from '~/components/IntroThanks.vue';

    export default {
        components: {
            AppHeaderSecondary,
            IntroThanks
        }
    }
</script>

<style>

</style>

