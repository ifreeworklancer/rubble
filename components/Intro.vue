<template>
    <section id="intro">
        <div class="intro-slider" ref="flickity">
            <div class="intro-slider-item" v-for="item in intro.introSlider" :key="item"
                 :style="{ backgroundImage: 'url(' + item + ')' }"></div>
        </div>
        <div class="container h-100 position-relative">
            <div class="row h-100">
                <div class="col-sm-9 col-lg-8 col-xl-7 h-100 d-flex align-items-center">
                    <div class="intro-item">
                        <h1 class="intro-item__title">
                            {{intro.title}}
                        </h1>
                        <div class="intro-item__subtitle">
                            {{intro.subtitle}}
                        </div>
                        <a href="#" @click.prevent="open" class="btn btn-primary">
                            Связаться
                        </a>
                    </div>
                </div>
            </div>
            <div class="slider-arrow">
                <div class="slider-arrow-item slider-arrow-item--prev slider-arrow-item--prev-intro">
                    <svg width="25" height="20">
                        <use xlink:href="#arrow-prev-icon"></use>
                    </svg>
                </div>
                <div class="slider-arrow-item slider-arrow-item--next slider-arrow-item--next-intro">
                    <svg width="25" height="20">
                        <use xlink:href="#arrow-next-icon"></use>
                    </svg>
                </div>
            </div>
            <div class="slider-nav">
                <div class="slider-nav-item slider-nav-item--index"></div>
                <div class="slider-nav-item slider-nav-item--separator">/</div>
                <div class="slider-nav-item slider-nav-item--last"></div>
            </div>
        </div>
    </section>
</template>

<script>

    export default {
        data() {
            return {
                flickityOptions: {
                    prevNextButtons: false,
                    cellAlign: 'left',
                    contain: true,
                    draggable: false,
                    wrapAround: false,
                },
                intro: require('../db').intro
            }
        },
        methods: {
            open() {
                this.$emit('open');
            }
        },
        mounted() {
            let introSlider = new Flickity(this.$refs.flickity, this.flickityOptions);

            let prevArrowIntro = document.querySelector('.slider-arrow-item--prev-intro');
            let introSliderIndex = document.querySelector('.slider-nav-item--index');

            introSliderIndex.innerText = introSlider.selectedIndex + 1;

            prevArrowIntro.addEventListener('click', function () {
                introSlider.previous(true, false);
                introSliderIndex.innerText = introSlider.selectedIndex + 1;
            });

            let nextArrowIntro = document.querySelector('.slider-arrow-item--next-intro');

            nextArrowIntro.addEventListener('click', function () {
                introSlider.next(true, false);
                introSliderIndex.innerText = introSlider.selectedIndex + 1;
            });

            let introSliderlast = document.querySelector('.slider-nav-item--last');

            introSliderlast.innerText = introSlider.getCellElements().length;
        },
    }
</script>

<style lang="scss" scoped>
    @import "../assets/app.scss";

    #intro {
        height: 700px;

        @media (min-width: map_get($grid-breakpoints, sm)) {
            height: 100vh;
            max-height: 1080px;
        }
    }

    .intro-item {

        &__title {
            margin-bottom: 0;
        }

        &__subtitle {
            font-size: 24px;
            margin: 30px 0;
        }
    }

    .intro-slider {
        @extend %pos;

        &-item {
            width: 100%;
            height: 700px;
            @extend %img;

            @media (min-width: map_get($grid-breakpoints, sm)) {
                height: 100vh;
                max-height: 1080px;
            }

            &::before {
                content: '';
                @extend %pos;
                background: rgba(#191f26, .65);
            }
        }
    }

    .slider-arrow {
        position: absolute;
        left: 0;
        bottom: 0;

        @media (min-width: map_get($grid-breakpoints, sm)) {
            left: 15px;
        }
    }

    .slider-nav {
        position: absolute;
        right: 0;
        bottom: 15px;
        display: flex;

        @media (min-width: map_get($grid-breakpoints, sm)) {
            right: 15px;
        }

        &-item {
            font-weight: bold;
            font-size: 18px;
            margin-right: 5px;

            &::before {
                content: '0';
            }

            &--separator {

                &::before {
                    content: '';
                }
            }
        }
    }
</style>

