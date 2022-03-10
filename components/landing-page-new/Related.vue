<template>
    <div class="related-section">
        <h1 class="related-section__heading highlight">
            Recent
        </h1>
        <div class="related-section__card-container">
            <VueSlickCarousel class="group" v-bind="settings">
                <a href="https://yy.ventures/news/go-green" target="_blank" class="related-section__card-container--link">
                    <div class="related-card">
                        <div class="related-card__img-container">
                            <img src="../../assets/images/landing-new-image/background-image/recent-1.jpg" alt="">
                        </div>
                        <p class="related-card__text">Go Green Bangladesh Named the Winner of Waste 2 Resources Program</p>
                    </div>
                </a>
                <a href="https://yy.ventures/news/sixth-anniversary" target="_blank" class="related-section__card-container--link">
                    <div class="related-card">
                        <div class="related-card__img-container">
                            <img src="../../assets/images/landing-new-image/background-image/recent-2.jpg" alt="">
                        </div>
                        <p class="related-card__text">6th Anniversary Celebration of the SDGs at the Embassy of the Netherlands in Bangladesh</p>
                    </div>
                </a>
                <a href="https://yy.ventures/news/best-aid-ltd" target="_blank" class="related-section__card-container--link">
                    <div class="related-card">
                        <div class="related-card__img-container">
                            <img src="../../assets/images/landing-new-image/background-image/recent-3.jpg" alt="">
                        </div>
                        <p class="related-card__text">YY Ventures Invests in Best Aid Limited</p>
                    </div>
                </a>
                <a href="https://yy.ventures/news/discussion-forum" target="_blank" class="related-section__card-container--link">
                    <div class="related-card">
                        <div class="related-card__img-container">
                            <img src="../../assets/images/landing-new-image/background-image/recent-4.jpg" alt="">
                        </div>
                        <p class="related-card__text">Discussion Forum Held on Opportunities & Challenges of Social Entrepreneurship in Bangladesh</p>
                    </div>
                </a>
                <a href="https://yy.ventures/news/bold-partnership" target="_blank" class="related-section__card-container--link">
                    <div class="related-card">
                        <div class="related-card__img-container">
                            <img src="../../assets/images/landing-new-image/background-image/recent-5.jpg" alt="">
                        </div>
                        <p class="related-card__text">A Bold Partnership Towards a World of Three Zeros</p>
                    </div>
                </a>
             </VueSlickCarousel>
        </div>
    </div>
</template>

<script>
    import VueSlickCarousel from 'vue-slick-carousel'
    import 'vue-slick-carousel/dist/vue-slick-carousel.css'
    import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'

    export default {
        name: 'MyComponent',
        components: { VueSlickCarousel },
        data() {
            return {
                settings: {
                    arrows: true,
                    slidesToShow: 3,
                    autoplay:true,
                    responsive: [
                        {
                            breakpoint: 601,
                            settings: {
                                arrows: true,
                                slidesToShow: 1,
                                autoplay: false
                            }
                        },
                    ]
                }
            }
        }
    }
</script>

<style lang="scss" scoped>
    .related-section{
        background: #323637;
        padding: 2rem 6rem;
        margin: 80px 40px;

        @media screen and (max-width:600px){
            padding: 2rem;
            margin: 40px;
        }

        &__heading{
            color: white;
            margin-bottom: 60px;
        }
        &__card-container{
            &--link{
                text-decoration: none;
            }
            .related-card{

                padding: 0 20px;
            
                &__img-container{
                    height: 200px;

                    img{
                        height: 100%;
                        object-fit: cover;
                    }
                }
                &__text{
                    color: white;
                    font-weight: 600;
                }
            }
        }
    }
</style>