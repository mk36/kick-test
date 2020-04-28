<style lang="scss">
    .showroom-images-section{
        .showroom-images{
            @include flex(100%, flex, unset, unset);
            &__row{
                display: flex;
                flex-direction: column;
                max-height: 500px;
                overflow: hidden;

                &.left-row{
                    flex-basis: 25%;

                    img{
                        flex-basis: 50%;
                    }
                }

                &.right-row{
                    flex-basis: 75%;

                    img:nth-child(1){
                        flex-basis: 30%;
                    }

                    .right-row__images{
                        flex-basis: 70%;
                        display: flex;

                        div{

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
                    <img :src="getImgUrl('images/showroom2.jpg')" alt="" class="showroom-images__row__img">

                    <div class="right-row__images">
                        <img :src="getImgUrl('images/showroom-4.jpg')" alt="" class="showroom-images__row__img">

                        <div>
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
