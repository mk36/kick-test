<style lang="scss" scoped>
    .kitchen-site{

    }
</style>

<template>
    <div class="kitchen-site">
       <site-header></site-header>
        <site-banner image="images/banner-image.jpg"></site-banner>

        <article>
            <design-service></design-service>
            <showrooms></showrooms>
            <showroom-images></showroom-images>
            <brands></brands>
            <fitting></fitting>
        </article>

        <site-footer></site-footer>
    </div>
</template>

<script>
    import "./styles/styles.scss";
    import SiteHeader from './components/site-header/site-header';
    import SiteBanner from './components/banners/banner';
    import DesignService from './components/sections/design-service/design-service';
    import Showrooms from './components/sections/showrooms/showrooms';
    import ShowroomImages from './components/sections/showrooms/showroom-images';
    import Brands from './components/sections/brands/brands';
    import Fitting from './components/sections/fitting/fitting';
    import SiteFooter from './components/site-footer/site-footer';

    export default {
        name: 'App',
        components: {
            SiteHeader,
            SiteBanner,
            DesignService,
            Showrooms,
            ShowroomImages,
            Brands,
            Fitting,
            SiteFooter
        }
    }
</script>
