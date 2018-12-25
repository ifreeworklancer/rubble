<template>
    <div>
        <div class="custom-modal custom-modal--order">
            <div class="close-modal">
                <div class="line line--left"></div>
                <div class="line line--right"></div>
            </div>
            <div class="custom-modal-header">
                <h3 class="section-title mb-4">
                    Оставте заявку, мы Вам перезвоним
                </h3>
            </div>
            <div class="custom-modal-body">
                <form method="post">
                    <input type="hidden" name="title" value="Заказ">
                    <input type="hidden" name="catalog_title">
                    <div class="form-column">
                        <div class="form-column">
                            <div class="form-group">
                                <input type="text" name="name" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <input type="tel" name="phone" class="form-control" required>
                            </div>
                            <div class="form-group form-group--btn">
                                <button type="submit" class="btn btn-dark">Отправить</button>
                            </div>
                        </div>
                    </div>
                </form>
            </div>
        </div>

        <div class="custom-modal custom-modal--connection">
            <div class="close-modal">
                <div class="line line--left"></div>
                <div class="line line--right"></div>
            </div>
            <div class="custom-modal-header">
                <h3 class="section-title mb-4">
                    Оставте заявку, мы Вам перезвоним
                </h3>
            </div>
            <div class="custom-modal-body">
                <form>
                    <input type="hidden" name="title" value="Свяжитесь с нами">
                    <div class="form-column">
                        <div class="form-group">
                            <input type="text" name="name" class="form-control" id="user-name" required>
                        </div>
                        <div class="form-group">
                            <input type="tel" name="phone" class="form-control" id="user-phone" required>
                        </div>
                        <div class="form-group form-group--btn">
                            <button type="submit" class="btn btn-dark">Отправить</button>
                        </div>
                    </div>
                </form>
            </div>
        </div>

        <div class="modal-mask"></div>
    </div>
</template>

<script>

    export default {}
</script>

<style lang="scss" scoped>
    @import "../assets/app.scss";

    .custom-modal {
        position: fixed;
        top: 50%;
        left: 50%;
        padding: 40px 30px 5px;
        width: 95%;
        max-width: 440px;
        background: $primary;
        z-index: 120;
        border-radius: 3px;
        transition: .5s;
        opacity: 0;
        pointer-events: none;
        transform: translate(-50%, -300%);

        &.active {
            opacity: 1;
            pointer-events: all;
            transform: translate(-50%, -50%);
        }

        .close-modal {
            position: absolute;
            top: 10px;
            right: 10px;
            width: 20px;
            height: 20px;
            cursor: pointer;

            &:hover {

                .line {
                    opacity: 1;
                }
            }

            .line {
                position: absolute;
                top: 50%;
                left: 50%;
                width: 20px;
                height: 1px;
                background: #fff;
                opacity: .7;

                &--left {
                    transform: translate(-50%, -50%) rotate(-45deg);
                }

                &--right {
                    transform: translate(-50%, -50%) rotate(45deg);
                }
            }
        }
    }


    .modal-mask {
        @extend %pos;
        position: fixed;
        background: rgba($dark, .8);
        opacity: 0;
        pointer-events: none;
        z-index: 119;
        transition: .5s;

        &.active {
            opacity: 1;
            pointer-events: all;
        }
    }

</style>

