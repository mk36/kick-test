<style lang="scss" scoped>
.mobile-menu{
    @include positioningOffset(fixed, 0, unset, unset, 0);
    z-index: $z-index-modal;
    width: 100%;
    height: 100vh;
    transition: transform 0.3s ease-in-out;
    transform: translateX(-110%);

    &.open{
        transform: translateX(0);
    }

    &__content{
        background-color: $blue;
        width: 300px;
        height: 100%;
        @include paddingBorderBox(25px);
        box-shadow: 0 0 5px 5px rgba(0,0,0,0.8);

        &__logo{
            margin-bottom: 15px;
            max-width: 50px;
        }

        &__nav{
            flex-direction: column;

            p{
                margin-bottom: 20px;
                color: $white;
            }
        }
    }
}
</style>

<template>
    <div class="mobile-menu" :class="{'open': open}" @click="closeMenu($event)">
        <section class="mobile-menu__content">
            <div class="mobile-menu__content__logo">
                <img class="site-header__logo__img" src="../../assets/logos/logo.png" alt="logo">
            </div>

            <nav class="mobile-menu__content__nav is-flex">
                <p @click="scrollToEmit('.site-banner')">Kitchens</p>
                <p @click="scrollToEmit('.design-service')">Design Service</p>
                <p @click="scrollToEmit('.showrooms')">Our Showrooms</p>
                <p @click="scrollToEmit('.brands')">Brands</p>
                <p @click="scrollToEmit('.fitting-section')">Fittings Service</p>
            </nav>
        </section>
    </div>
</template>

<script>
    export default {
        components: {},
        props:['open'],
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
            closeMenu(event){
                let vm = this;

                if(event.target.classList.contains('open')){
                    vm.$emit('close', true);
                }
            },
            scrollToEmit(selector){
                this.$emit('scroll-to', selector);
            }
        }
    }
</script>
