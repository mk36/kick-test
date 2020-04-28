<style lang="scss">
.design-service-option{
    @include mobile-tablet{
        &:not(:last-child){
            @include paddingBorderBox(0 0 15px 0);
        }
    }

    @include tablet-landscape{
        @include paddingBorderBox(0 15px 0 0 !important);
    }

    @include desktop{
        @include paddingBorderBox(0 15px 0 0);
    }

    &__image{
        height: 175px;
        object-fit: cover;

        @include tablet{
            height: 250px;
        }
    }

    &__title{
        font-weight: 600;
    }
}
</style>

<template>
    <section class="design-service-option">
        <img :src="getImgUrl(image)" alt="" class="design-service-option__image">
        <h4 class="design-service-option__title title-blue">{{title}}</h4>
        <p class="design-service-option__text">{{text}}</p>
    </section>
</template>

<script>
    export default {
        components: {},
        props:['image','title', 'text'],
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
