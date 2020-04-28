<style lang="scss">
    .site-footer{
        background-color: $grey-light;
        @include paddingBorderBox(25px);

        @include desktop{
            @include paddingBorderBox(25px 0);
        }

        &__details{
            @include flex(100%, flex, space-between, center);
            flex-wrap: wrap;

            @include desktop{
                flex-wrap: unset;
            }

            &__contact{
                a{
                    display: block;

                    @include desktop{
                        margin-left: 25px;
                        display: initial;
                    }
                }
            }

            &__social{
                a{
                    &:not(:last-child){
                        img{
                            margin-right: 10px;
                        }
                    }

                    img{
                        max-width: 30px;
                    }
                }
            }
        }

        hr{
            width: 100%;
            border: 1px solid darkgray;
            margin: 10px 0;
        }

        &__copyright{
            color: #707070;
            font-size: 8pt;
        }
    }
</style>

<template>
    <footer class="site-footer">
        <div class="max-head-foot-width full">
            <section class="site-footer__details">
                <p class="site-footer__details__contact">
                    0800 2100 458 <a href="mailto:enquiries@kitchens.biz">enquiries@kitchens.biz</a>
                </p>
                <section class="site-footer__details__social">
                    <a href=""><img :src="getImgUrl('icons/Social/White/facebook.png')" alt="social icon"></a>
                    <a href=""><img :src="getImgUrl('icons/Social/White/twitter.png')" alt="social icon"></a>
                    <a href=""><img :src="getImgUrl('icons/Social/White/linked.png')" alt="social icon"></a>
                </section>
            </section>

            <hr>

            <p class="site-footer__copyright">
                Company Group - Copyright © 2019. All Rights Reserved all 3rd party trademarks acknowledged.
            </p>
        </div>
    </footer>
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
                return require('../../assets/'+ url);
            }
        }
    }
</script>
