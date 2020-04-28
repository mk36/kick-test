<style lang="scss">
.showrooms{
    text-align: center;

    &__title{
        font-weight: 600;
        padding-bottom: 10px;
    }
}
</style>

<template>
    <section class="showrooms grey-background section-padding">
        <div class="max-content-width full">
            <h3 class="showrooms__title">OUR SHOWROOMS</h3>

            <p class="showrooms__text">
                Our main kitchen showroom is in Brighton where you can discuss your options with our designers. We can show you plenty of projects we’ve worked on. We’ve designed kitchens from small bedsits to large housing developments & luxury homes. Our extensive range includes both contemporary & traditional kitchens; all are competitively priced so we can work with you whether you’re looking for low budget or high end designer style. We also have smaller kitchen showrooms at our Petworth and Chertsey branches where you can pick up a brochure detailing our full range.
            </p>
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

            }
        }
    }
</script>
