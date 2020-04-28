<style lang="scss">
.design-service-option{
    &:not(:last-child){
        @include paddingBorderBox(0 0 15px 0);
    }

    @include desktop{
        @include paddingBorderBox(0 15px 0 0);
    }

    &__image{
        height: 175px;
        object-fit: cover;
    }

    &__title{
        font-weight: 600;
    }
}
</style>

<template>
    <section class="design-service-option">
        <img :src="getImgUrl(image)" alt="" class="design-service-option__image">
        <h4 class="design-service-option__title">{{title}}</h4>
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
