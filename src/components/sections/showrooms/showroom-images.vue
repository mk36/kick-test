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
                        }

                        img, &__nested{
                            flex-basis: 50%;
                        }

                        &__nested{
                            @include flex(100%, flex, center, center);
                            flex-direction: column;

                            img:nth-child(1){
                                @include paddingBorderBox(0 0 $image-padding 0);
                            }
                        }
                    }
                }
            }
        }
    }
</style>

<template>
    <section class="showroom-images-section section-padding">
        <div class="max-content-width full">
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
    </section>
</template>

<script>
    export default {
        components: {},
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
