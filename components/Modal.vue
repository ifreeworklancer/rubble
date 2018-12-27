<template>
    <transition name="modal-fade">
        <div class="custom-modal-backdrop">
            <div class="custom-modal" role="dialog" aria-labelledby="modalTitle" aria-describedby="modalDescription">
                <div class="custom-modal-header" id="modalTitle">
                    <slot name="header">
                        <h2 class="title mb-5">Оставьте заявку</h2>
                        <div @click="close" class="close-modal">
                            <div class="line line--left"></div>
                            <div class="line line--right"></div>
                        </div>
                    </slot>
                </div>
                <div class="custom-modal-body" id="modalDescription">
                    <slot name="body">
                        <form-column></form-column>
                    </slot>
                </div>
            </div>
        </div>
    </transition>
</template>

<script>
    import FormColumn from '~/components/FormColumn.vue';
    export default {
        methods: {
            close() {
                this.$emit('close');
            },
        },
        components: {
            FormColumn
        }
    };
</script>

<style lang="scss">

    .modal-fade-enter,
    .modal-fade-leave-active {
        opacity: 0;
    }

    .modal-fade-enter-active,
    .modal-fade-leave-active {
        transition: opacity 1s ease
    }

    .custom-modal-backdrop {
        position: fixed;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: rgba(#333, .8);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 119;
    }

</style>