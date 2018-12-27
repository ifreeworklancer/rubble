<template>
    <header id="app-header">
        <div class="container-fluid px-sm-5">
            <div class="row justify-content-between align-items-center">
                <div class="col-auto">
                    <nuxt-link to="/" class="logo">
                        LOGO
                    </nuxt-link>
                </div>
                <div class="col-6">
                    <div class="header-contacts">
                        <ul class="contacts-list d-none d-lg-flex">
                            <li><a :href="'tel:' + contacts.phone[0]">{{ contacts.phone[0] }}</a></li>
                            <li><a :href="'tel:' + contacts.phone[1]">{{ contacts.phone[1] }}</a></li>
                            <li><a :href="'mailto:' + contacts.email">{{ contacts.email }}</a></li>
                        </ul>
                        <nuxt-link to="/" class="btn btn-outline-primary open-connection">
                            На главную
                        </nuxt-link>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<script>

    export default {
        data() {
            return {
                contacts: require('../db').contacts
            }
        }
    }
</script>

<style lang="scss">
    #app-header {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        padding: 30px 0;
        background: rgba(#000, .3);
        z-index: 200;

        .logo {
            font-family: 'Montserrat', sans-serif;
            color: #fff;
        }
    }

    .header-contacts {
        display: flex;
        justify-content: flex-end;
        align-items: center;

        .contacts-list {
            margin-right: 60px;
        }
    }
</style>