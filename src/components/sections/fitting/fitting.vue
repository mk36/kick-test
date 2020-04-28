<style lang="scss">
    .fitting-section{
        display: flex;
        flex-wrap: wrap;

        &__image{
            @include paddingBorderBox(0 0 25px 0);
            max-height: 300px;
            object-fit: cover;

            @include desktop{
                max-width: 50%;
                max-height: unset;
                flex-basis: 50%;
                @include paddingBorderBox(0 25px 0 0);
            }
        }

        &__text{
            @include desktop{
                flex-basis: 50%;
                order: unset;
            }

            &__item{
                padding-bottom: 25px;
                &__title{
                    font-weight: 600;
                    padding-bottom: 10px;
                }
            }
        }

        &__options{
            display: flex;
            flex-wrap: wrap;

            @include tablet-landscape{
                padding-top: 25px !important;
            }

            @include mobile-tablet{
                padding: 0;
            }

            @include desktop{
                flex-wrap: unset;
            }
        }
    }
</style>

<template>
    <section class="fitting-section-wrapper section-padding">
        <div class="max-content-width full">
            <section class="fitting-section">
                <img :src="getImgUrl('images/fitting-service.jpg')" alt="" class="fitting-section__image">

                <section class="fitting-section__text">
                    <div class="fitting-section__text__item">
                        <h3 class="fitting-section__text__item__title title-blue">FITTING SERVICE</h3>

                        <p>
                            To get the very best from your new kitchen, Chandlers can fi t  it for you too. We offer a dry fit installation service, which includes worktop fitting. By choosing us to install your kitchen we will fully project manage the installation, carried out by our experienced fitters. The work is not complete until the kitchen is signed off to your satisfaction.
                        </p>

                        <p>
                            Our dry fit installation includes the installation of all units, trims, panels, appliances, worktops and splashbacks. You will only need to arrange plumbing, electrical connections and decoration. The fitting service is available for any number of kitchens from 1 to 100.
                        </p>
                    </div>

                    <div class="fitting-section__text__item">
                        <h3 class="fitting-section__text__item__title title-blue">A KITCHEN DESIGNED JUST FOR YOU</h3>

                        <p>
                            Using our designers will help you to get the absolute maximum from your space. Our experience and expertise enables us to not only see the simple ideas but come up with some innovative ones too. Whether we visit you on site or you visit the showroom, we have a full range of samples and offer a complete site measurement service also
                        </p>

                        <p>
                            All our units have soft close doors and drawers as standard and, we offer a competitively priced modification service for the creation of bespoke size units. We work to your time scales, you can expect delivery 3 weeks from placing your order (painted kitchens carry a 4 week lead time).
                        </p>
                    </div>
                </section>
            </section>

            <section class="fitting-section__options section-padding">
                <fitting-option v-for="(option, index) in fittingOptions" :key="index" :text="option.text" :title="option.title" :image="'images/' + option.image"></fitting-option>
            </section>

        </div>
    </section>
</template>

<script>
    import FittingOption from './fitting-option';
    export default {
        components: {FittingOption},
        props:[''],
        data: function(){
            return{
                fittingOptions: [
                    {
                        image: "TrueRigidCabinets.jpg",
                        title: "True Rigid Cabinets",
                        text: "Our cabinets are made using traditional glue and dowel techniques, ensuring there are no visible fixings or redundant drill holes. They arrive fully assembled."
                    },
                    {
                        image: "app.jpg",
                        title: "Appliances",
                        text: "At Chandlers Building Supplies, we offer a comprehensive range of kitchen appliances from Bosch, Neff, Siemens, Smeg to suit all cooking levels and budget"
                    },
                    {
                        image: "Worksurfaces.jpg",
                        title: "Worksurfaces",
                        text: "Here at Chandlers Building Supplies,we can supply:Laminate / Glass / Granite / Quartz / Dekton & Corian worksurfaces and/or splashbacks"
                    }
                ]
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
