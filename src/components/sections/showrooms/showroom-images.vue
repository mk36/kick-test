<style lang="scss">
    .showroom-images-section{
        .showroom-images{
            @include flex(100%, flex, unset, unset);
            $image-padding: 25px;

            &__row{
                display: flex;
                flex-direction: column;
                max-height: 700px;

                img{
                    object-fit: cover;
                }

                &.left-row{
                    flex-basis: 45%;
                    @include paddingBorderBox(0 $image-padding 0 0);

                    img{
                        &:first-child{
                            flex-basis: 35%;
                            @include paddingBorderBox(0 0 $image-padding 0);
                        }

                        &:nth-child(2){
                            flex-grow: 1;
                        }
                    }
                }

                &.right-row{
                    flex-basis: 65%;

                    .first-image{
                        flex-basis: 30%;
                        max-height: 40%;
                        @include paddingBorderBox(0 0 $image-padding 0);
                    }

                    .right-row__images{
                        flex-basis: 70%;
                        display: flex;

                        .first-nested-image{
                            @include paddingBorderBox(0 $image-padding 0 0);
                            max-height: 50%;
                        }

                        img, &__nested{
                            flex-basis: 50%;
                        }

                        &__nested{
                            @include flex(100%, flex, left, center);
                            flex-direction: column;

                            img{
                                max-height: 25%;
                            }

                            img:nth-child(1){
                                @include paddingBorderBox(0 0 $image-padding 0);
                            }
                        }
                    }
                }
            }
        }

        .showroom-carousel{
            img{
                max-height: 200px;
                object-fit: cover;
            }

            .VueCarousel-dot-container{
                margin-top: 0 !important;
            }
        }
    }
</style>

<template>
    <section class="showroom-images-section section-padding">
        <div class="max-content-width full is-hidden-touch">
            <section class="showroom-images">
                <div class="showroom-images__row left-row">
                    <img :src="getImgUrl('images/showroom-1.jpg')" alt="" class="showroom-images__row__img">
                    <img :src="getImgUrl('images/showroom3.jpg')" alt="" class="showroom-images__row__img">
                </div>

                <div class="showroom-images__row right-row">
                    <img :src="getImgUrl('images/showroom2.jpg')" alt="" class="showroom-images__row__img first-image">

                    <div class="right-row__images">
                        <img :src="getImgUrl('images/showroom-4.jpg')" alt="" class="showroom-images__row__img first-nested-image">

                        <div class="right-row__images__nested">
                            <img :src="getImgUrl('images/showroom_5.jpg')" alt="" class="showroom-images__row__img">
                            <img :src="getImgUrl('images/showroom6.jpg')" alt="" class="showroom-images__row__img">
                        </div>
                    </div>
                </div>
            </section>
        </div>

        <div class="is-hidden-desktop showroom-carousel">
            <carousel paginationColor="gray" paginationActiveColor="#0E4865" :perPage="1">
                <slide>
                    <img :src="getImgUrl('images/showroom-1.jpg')" alt="" class="showroom-carousel__img">
                </slide>
                <slide>
                    <img :src="getImgUrl('images/showroom3.jpg')" alt="" class="showroom-carousel__img">
                </slide>
                <slide>
                    <img :src="getImgUrl('images/showroom2.jpg')" alt="" class="showroom-carousel__img">
                </slide>
                <slide>
                    <img :src="getImgUrl('images/showroom-4.jpg')" alt="" class="showroom-carousel__img">
                </slide>
                <slide>
                    <img :src="getImgUrl('images/showroom_5.jpg')" alt="" class="showroom-carousel__img">
                </slide>
                <slide>
                    <img :src="getImgUrl('images/showroom6.jpg')" alt="" class="showroom-carousel__img">
                </slide>
            </carousel>
        </div>
    </section>
</template>

<script>
    import { Carousel, Slide } from 'vue-carousel';
    export default {
        components: {
            Carousel,
            Slide
        },
        props:[''],
        data: function(){
            return{
                test: ''
            }
        },
        mounted: function () {
            this.setUp();
        },
        methods: {
            setUp: function () {

            },
            getImgUrl(url) {
                return require('../../../assets/'+ url);
            }
        }
    }
</script>
