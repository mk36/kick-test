<style lang="scss">
    .design-service{
        text-align: center;

        &__title{
            font-weight: 600;
            padding-bottom: 10px;
        }

        &__options{
            display: flex;
            flex-wrap: wrap;

            @include mobile-tablet{
                padding-left: 0;
                padding-right: 0;
            }

            @include desktop{
                flex-wrap: unset;
            }
        }
    }
</style>

<template>
    <section class="design-service section-padding">
        <div class="max-content-width full">
            <h3 class="design-service__title">KITCHEN DESIGN SERVICE</h3>

            <p class="design-service__text">
                Buying a new kitchen can be a daunting task. There are many special offers and huge variations in price, quality and service.
                We try to make things simple by offering you a visual of your new kitchen with our free design service.
                We will show you 3D drawings and photo realistic images of the proposed design because we think its always advisable to see your new kitchen in the style and finish of your choice before you actually buy it.
            </p>

            <section class="design-service__options section-padding">
                <design-service-option v-for="(option, index) in designOptions" :key="index" :text="option.text" :title="option.title" :image="'images/' + option.image"></design-service-option>
            </section>
        </div>
    </section>
</template>

<script>
    import DesignServiceOption from './design-service-option';
    export default {
        components: { DesignServiceOption },
        props:[''],
        data: function(){
            return{
                designOptions: [
                    {
                        image: "design-service-1.jpg",
                        title: "Development Kitchens",
                        text: "Specialist and experienced design team available to work with you, delivering your project on time and within budget"
                    },
                    {
                        image: "design-service-2.jpg",
                        title: "Trade Kitchens",
                        text: "Free kitchen survey and design services available to the trade including 3D visuals. Call 01273 420364"
                    },
                    {
                        image: "design-service-3.jpg",
                        title: "Contract Kitchens",
                        text: "For the larger contractor, we are able to oﬀer a tailored solution to meet your exact speciﬁcations on any development"
                    }
                ]
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
