<template>
    <footer id="app-footer">
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <div class="footer-copyr text-center">
                        Copyright 2018  © All Rights Reserved | Developed by <a href="https://impressionbureau.pro/" target="_blank">Impression Bureau</a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
    @import "../assets/app.scss";

    #app-footer {
        padding: 20px 0;
        background: $dark;
    }

    .footer-copyr {
        font-weight: 300;
        color: #cecece;
        
        a {
            font-weight: bold;
            color: #fff;
        }
    }
</style>