<style lang="scss">
.brands{
    text-align: center;

    &__title{
        font-weight: 600;
        padding-bottom: 10px;
    }

    &__images{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;

        img{
            flex-basis: 50%;

            &:not(:last-child){
                margin: 5px 0;
            }
        }

        @include desktop{
            flex-wrap: unset;
            margin: 0;
        }
    }
}
</style>

<template>
    <section class="brands grey-background section-padding">
        <div class="max-content-width full">
            <h3 class="brands__title title-blue">LEADING BRANDS IN STORE</h3>

            <div class="brands__images">
                <img :src="getImgUrl('logos/new/quooker.png')" alt="logo">
                <img :src="getImgUrl('logos/new/bosch.png')" alt="logo">
                <img :src="getImgUrl('logos/new/siemens.png')" alt="logo">
                <img :src="getImgUrl('logos/new/neff.png')" alt="logo">
                <img :src="getImgUrl('logos/new/smeg.png')" alt="logo">
            </div>
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
