<style lang="scss">
.site-banner{
    width: 100%;
    height: 275px;
    position: relative;
    @include setBackgroundImage('~../../assets/images/banner-image.jpg');

    &__text{
        font-weight: 600;
        text-transform: uppercase;
        @include centerContent();
        text-align: center;
    }
}
</style>

<template>
    <section class="site-banner">
        <h2 class="site-banner__text">Our bespoke kitchens</h2>
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

            }
        }
    }
</script>
