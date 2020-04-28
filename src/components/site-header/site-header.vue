<style lang="scss">
.site-header{
    background-color: $blue;
    height: $header-height;
    display: flex;

    &__logo{
        max-width: 100vw;
        @include flex(100%, flex, space-between, center);

        img{
            max-width: 60px;
            cursor: pointer;
        }

        .mobile-menu-icon{
            color: $white;
            font-size: 22pt;
        }
    }

    &__navigation{
        @include flex(100%, flex, left, center);

        p{
            font-size: $small-nav-font;
            font-weight: 600;
            color: $white;
            padding-right: 20px;
            cursor: pointer;

            &:hover{
                text-decoration: underline;
            }
        }
    }

    .site-header-columns{
        @include flex(100%, flex, space-between, center);
    }

}
</style>

<template>
    <header class="site-header navbar is-fixed-top">
        <div class="max-head-foot-width full">
            <div class="site-header-columns">
                <div class="column is-two-fifths-desktop site-header__logo">
                    <img @click="scrollToSection('.site-banner')" src="../../assets/logos/logo.png" alt="" class="site-header__logo">
                    <i @click="mobileMenuOpen = true" class="fa fa-bars mobile-menu-icon is-hidden-desktop" aria-hidden="true"></i>
                </div>
                <div class="column is-hidden-touch">
                    <nav class="site-header__navigation">
                        <p @click="scrollToSection('.site-banner')">Kitchens</p>
                        <p @click="scrollToSection('.design-service')">Design Service</p>
                        <p @click="scrollToSection('.showrooms')">Our Showrooms</p>
                        <p @click="scrollToSection('.brands')">Brands</p>
                        <p @click="scrollToSection('.fitting-section')">Fittings Service</p>
                    </nav>
                </div>
            </div>
        </div>

        <mobile-menu @scroll-to="mobileMenuOpen = false; scrollToSection($event)" @close="mobileMenuOpen = false" :open="mobileMenuOpen"></mobile-menu>
    </header>
</template>

<script>
    import MobileMenu from './mobile-menu';
    export default {
        components: {
            MobileMenu
        },
        props:[''],
        data: function(){
            return{
                mobileMenuOpen: false
            }
        },
        mounted: function () {
            this.setUp();
        },
        methods: {
            setUp: function () {

            },
            /**
             * scroll to a section
             * @param id
             */
            scrollToSection(selector){
                let elm = document.querySelector(selector);

                if(elm){
                    elm.scrollIntoView({ behavior: 'smooth', block: 'center'})
                }
            }
        }
    }
</script>
