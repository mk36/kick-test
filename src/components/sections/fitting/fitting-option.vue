<style lang="scss">
.fitting-option{
    @include paddingBorderBox(0 0 20px 0);

    @include desktop{
        @include paddingBorderBox(0 20px 0 0);
    }

    &__image{
        height: 175px;
        object-fit: cover;
        margin-bottom: -10px;
    }

    &__content{
        background-color: $blue;
        color: $white;
        text-align: center;
        @include paddingBorderBox(15px);
    }

    &__title{
        font-weight: 600;
    }

    &__text{
        font-size: 10pt;
    }
}
</style>

<template>
    <section class="fitting-option">
        <img :src="getImgUrl(image)" alt="" class="fitting-option__image">
        <div class="fitting-option__content">
            <h4 class="fitting-option__title">{{title}}</h4>
            <p class="fitting-option__text">{{text}}</p>
        </div>

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
