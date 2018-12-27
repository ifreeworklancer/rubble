<template>
    <form v-on:submit.prevent="onSubmit">
        <div class="form-column">
            <div class="form-group">
                <input v-model="userName" type="text" name="user_name" class="form-control" placeholder="Ваше имя">
            </div>
            <div class="form-group">
                <input v-model="userPhone" type="tel" name="user_phone" class="form-control" placeholder="Номер телефона">
            </div>
            <div class="form-group">
                <input v-model="userEmail" type="email" name="user_email" class="form-control" placeholder="Email">
            </div>
            <button type="submit" class="btn btn-outline-primary">Отправить</button>
        </div>
    </form>
</template>

<script>

    export default {
        data() {
            return {
                userName: '',
                userPhone: '',
                userEmail: ''
            }
        },
        methods: {
            onFocus(event) {
                event.target.parentNode.classList.add('in-focus');
                event.target.parentNode.querySelector('input').focus();
            },
            onBlur(e) {
                if (e.target.value !== "") {
                    e.target.parentNode.classList.add('in-focus');
                } else {
                    e.target.parentNode.classList.remove('in-focus');
                }
            },
            onSubmit() {
                console.log(`Name: ${this.userName}\n Phone: ${this.userPhone}\n Email: ${this.userEmail}\n`);
            }
        },
    }
</script>

<style lang="scss" scoped>
    @import "../assets/app.scss";

    .form-group {
        position: relative;

        .form-control {
            padding: 10px 15px;
            background: $secondary;
            border-radius: 4px;
            border: none;
            color: #fff;
            transition: .5s;

            &::placeholder {
                color: #fff;
            }
        }
    }

    .form-column {

        .form-group {
            width: 100%;
            margin-bottom: 40px;
        }

        &--min {
            max-width: 315px;
        }
    }
</style>
