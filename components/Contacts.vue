<template>
    <section id="contacts">
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <h2 class="section-title text-center mb-5">
                        Наши контакты
                    </h2>
                </div>
                <div class="col-lg-4">
                    <div class="contacts-item">
                        <div class="content">
                            <h3 class="title">
                                <div class="icon">
                                    <svg width="15" height="20">
                                        <use xlink:href="#address-icon"></use>
                                    </svg>
                                </div>
                                <span class="text">Наш офис</span>
                            </h3>
                            <ul class="contacts-list">
                                <li class="contacts-list-item">
                                    <a :href="contacts.addressLink" target="_blank">{{contacts.address}}</a>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="col-lg-4">
                    <div class="contacts-item">
                        <div class="content">
                            <h3 class="title">
                                <div class="icon">
                                    <svg width="20" height="20">
                                        <use xlink:href="#phone-icon"></use>
                                    </svg>
                                </div>
                                <span class="text">Телефоны</span>
                            </h3>
                            <ul class="contacts-list">
                                <li><a :href="'tel:' + contacts.phone[0]">{{ contacts.phone[0] }}</a></li>
                                <li><a :href="'tel:' + contacts.phone[1]">{{ contacts.phone[1] }}</a></li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="col-lg-4">
                    <div class="contacts-item">
                        <div class="content">
                            <h3 class="title">
                                <div class="icon">
                                    <svg width="20" height="15">
                                        <use xlink:href="#email-icon"></use>
                                    </svg>
                                </div>
                                <span class="text">Email</span>
                            </h3>
                            <ul class="contacts-list">
                                <li><a :href="'mailto:' + contacts.email">{{ contacts.email }}</a></li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="col-12 text-center">
                    <a href="#" @click.prevent="open" class="btn btn-outline-primary">
                        Связаться
                    </a>
                </div>
            </div>
        </div>
    </section>
</template>

<script>


    export default {
        data() {
            return {
                contacts: require('../db').contacts
            }
        },
        methods: {
            open() {
                this.$emit('open');
            }
        }
    }

</script>

<style lang="scss" scoped>
    @import "../assets/app.scss";

    #contacts {
        padding: 70px 0;
        background: #111111;
    }

    .contacts-item {
        display: flex;
        justify-content: center;
        align-items: center;
        margin-bottom: 35px;

        .title {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 20px;

            @media (min-width: map_get($grid-breakpoints, lg)) {
                justify-content: flex-start;
            }

            .icon {

                svg {
                    fill: $primary;
                }
            }

            .text {
                margin-left: 15px;
            }
        }
    }

    .contacts-list {

        li {

            a {
                font-weight: 300;
                color: #cecece;
            }
        }
    }

</style>

