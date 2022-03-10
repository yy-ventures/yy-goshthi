<template>
    <div class="how-we-help">
        <div class="how-we-help__heading-container">
            <div id="how"></div>
            <div id="we-help"></div>
        </div>
        <div class="how-we-help__training program-container faded_out">
            <div class="layer">
                <!-- <img class="image" src="../../assets/images/programs/wct.png" alt=""> -->
                <div class="text-container">
                    <h3 class="heading highlight">World Class Training</h3>
                    <p class="description">YY Goshthi creates a space for promising entrepreneurs to accelerate their business to the next level. The participants can draw guidelines and construct their business idea in the presence of world reputed business trainers. Our boot camp prepares the participants with different aspects of launching a successful business.</p>
                </div>
            </div>
        </div>
        <div class="how-we-help__consultation-support program-container faded_out">
            <div class="layer">
                <!-- <img class="image" src="../../assets/images/programs/mentoring.png" alt=""> -->
                <div class="text-container">
                    <h3 class="heading"> <span>Tailor Made</span> <span class="highlight">Consultation Support</span></h3>
                    <p class="description">One of the key benefits that we offer to our incubees is need based consultation support. We structure consultation hours based on the needs of the founders. In partnership with our supporters and network, we bring seasoned professionals, coaches and entrepreneurs from around the world to mentor our incubees.</p>
                </div>
            </div>
        </div>
        <div class="how-we-help__investor program-container faded_out">
            <div class="layer">
                <!-- <img class="image" src="../../assets/images/programs/investor.jpeg" alt=""> -->
                <div class="text-container">
                    <h3 class="heading"> <span>Investor</span> <span class="highlight">Network</span></h3>
                    <p class="description">Each cohort we offer pre-seed investment up to BDT 1.0- 1.5 million to top incubees and work with dozens of local and international investors and angels. We become partners with our incubees and help them negotiate and raise capital from investors.</p>
                </div>
            </div>
        </div>
        <div class="how-we-help__office-space program-container faded_out">
            <div class="layer">
                <!-- <img class="image" src="../../assets/images/programs/office_space.png" alt=""> -->
                <div class="text-container">
                    <h3 class="heading highlight">Office Space</h3>
                    <p class="description">We offer co-working space facility to our incubees at Impact Hub Dhaka, one of the world's largest networks focused on building entrepreneurial communities for impact scale, which brings together entrepreneurs, enablers, young talents and professionals from all across Bangladesh to create a vibrant community. For the first four months, our incubees are able to avail workspace without any expense.</p>
                </div>
            </div>
        </div>
        <div class="how-we-help__business-support program-container faded_out">
            <div class="layer">
                <!-- <img class="image" src="../../assets/images/programs/business_service.png" alt=""> -->
                <div class="text-container">
                    <h3 class="heading"><span>Pro-Bono Business</span> <span class="highlight">Support Services</span></h3>
                    <p class="description">Our sister organization, YY Studio specializes in creating strong brand identity, websites, and marketing collateral. As part of the incubation program, YY Studio offers business support services to our incubees pro-bono or at a minimum expense. Our partner organizations offer pro-bono legal and accounting support and we get access to new business opportunities with their help.</p>
                </div>
            </div>
        </div>
        <div class="how-we-help__community program-container faded_out">
            <div class="layer">
                <!-- <img class="image" src="../../assets/images/programs/sc.jpeg" alt=""> -->
                <div class="text-container">
                    <h3 class="heading highlight">Community</h3>
                    <p class="description">Get connected to our thriving community of compassionate, creative, and committed social entrepreneurs who aim to achieve collective progress through collaboration and exchange. Our community promotes a responsible and sustainable corporate culture and offers events, meetings, and activities that promote sustainability and entrepreneurship.</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import { add_class_on_focus } from '@/assets/scripts/dom_utils';

    export default {
        data(){
            return{
                pageY: null,
            }
        },
        mounted: () => {
            add_class_on_focus({
            ['.faded_out']: 'fade_in',
            });

            window.addEventListener('scroll', function(){
                let pageY = window.pageYOffset;
                const mediaQueryTab = window.matchMedia('(max-width: 960px)');
                const mediaQueryMob = window.matchMedia('(max-width: 600px)');
                const mediaQuerySmallMob = window.matchMedia('(max-width: 480px)');

                let how = document.querySelector('#how');
                let weHelp = document.querySelector('#we-help');

                how.style.backgroundPosition = `${pageY * 0.55 - 900}px`;
                weHelp.style.backgroundPosition = `${-pageY * 0.55 + 1800}px`;

                if(mediaQueryTab.matches) {
                    how.style.backgroundPosition = `${pageY * 0.55 - 1250}px`;
                    weHelp.style.backgroundPosition = `${-pageY * 0.6 + 2000}px`;
                }
                if(mediaQueryMob.matches) {
                    how.style.backgroundPosition = `${pageY * 0.55 - 1350}px`;
                    weHelp.style.backgroundPosition = `${-pageY * 0.6 + 1800}px`;
                }
                if(mediaQuerySmallMob.matches) {
                    how.style.backgroundPosition = `${pageY * 0.55 - 1100}px`;
                    weHelp.style.backgroundPosition = `${-pageY * 0.6 + 1400}px`;
                }
            });
        },
    };
</script>

<style lang="scss" scoped>
    .how-we-help{
        margin: 80px 40px;
        overflow: hidden;

        display: grid;
        grid-template-columns: [col-full-start col-lg-start] 70% [col-lg-end col-sm-start] 30% [col-sm-end col-full-end];
        grid-template-rows: [row-heading-start] min-content [row-heading-end] repeat(4, [row-start] 500px [row-end]);
        grid-gap: 10px;

        @media screen and (max-width:960px){
            grid-template-rows: [row-heading-start] min-content [row-heading-end] repeat(4, [row-start] 400px [row-end]);
        }

        @media screen and (max-width:600px){
            grid-template-columns: [col-start] 1fr [col-end];
            grid-template-rows: [row-heading-start] min-content [row-heading-end] repeat(6, [row-start] 300px [row-end]);

            margin: 40px;
        }

        &__heading-container{
            grid-column: col-full-start / col-full-end;
            grid-row: row-heading-start / row-heading-end;

            @media screen and (max-width:600px){
                grid-column: col-start / col-end;
                grid-row: row-heading-start / row-heading-end;
            }

            background-color: #EAECEB;
            padding: 40px 0;

            #how, #we-help{
                background-repeat: no-repeat;
                background-size: contain;
                height: 80px;

                @media screen and (max-width: 600px){
                    height: 70px;
                }
                @media screen and (max-width: 480px){
                    height: 50px;
                }
            }
            #how{
                background-image: url('../../assets/images/landing-new-image/animated-text/text-how.png');
                margin-bottom: 20px;
            }
            #we-help{
                background-image: url('../../assets/images/landing-new-image/animated-text/text-we_help.png');
            }
        }

        .program-container{
            background-size: cover;
            background-repeat: no-repeat;
            background-position: center;

            position: relative;
        }
        &__training{
            background-image: url('../../assets/images/landing-new-image/background-image/how-we-help-training.png');
        }
        &__consultation-support{
            background-image: url('../../assets/images/landing-new-image/background-image/how-we-help-consultation.png');
        }
        &__investor{
            background-image: url('../../assets/images/landing-new-image/background-image/investor-network.jpg');
            background-position: center !important;
        }
        &__office-space{
            background-image: url('../../assets/images/landing-new-image/background-image/office-space.jpg');
        }
        &__business-support{
            background-image: url('../../assets/images/landing-new-image/background-image/how-we-help-business_support.png');
        }
        &__community{
            background-image: url('../../assets/images/landing-new-image/background-image/how-we-help-community.png');
            background-position: top !important;
        }

        .layer{
            background-color: rgba(0, 0, 0, 0.6);
            padding: 20px;

            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;

            display: flex;
            align-items: flex-end;

            @media screen and (max-width:600px){
                padding: 2rem;
            }

            @media screen and (max-width:480px){
                padding: 10px;
            }


            p{
                padding: 0;
                margin: 0;
                color: white;
                font-size: 13px;
                line-height: 1.5;

                @media screen and (max-width:960px){
                    font-size: 11px;
                }
            }

            .heading{
                font-size: 40px;
                font-weight: 900;
                color: white;

                @media screen and (max-width:960px){
                    font-size: 30px;

                    span{
                        display: block;
                        white-space: nowrap;
                        width: min-content;
                    }
                }

                @media screen and (max-width:480px){
                    font-size: 25px;
                }
            }

            .text-container{
                max-width: 600px;
                
                .description{
                    font-size: 16px;

                    @media screen and (max-width: 600px){
                        font-size: 13px;
                    }
                }
            }
        }

        &__training{
            grid-column: col-full-start / col-full-end;
            grid-row: row-start 1 / row-end 1;
            
            @media screen and (max-width:600px){
                grid-column: col-start / col-end;
                grid-row: row-start 1 / row-end 1;
            }
            
        }
        &__consultation-support{
            grid-column: col-lg-start / col-lg-end;
            grid-row: row-start 2 / row-end 2;

            @media screen and (max-width:600px){
                grid-column: col-start / col-end;
                grid-row: row-start 2 / row-end 2;
            }
        }
        &__investor{
            grid-column: col-sm-start / col-sm-end;
            grid-row: row-start 2 / row-end 2;

            @media screen and (max-width:600px){
                grid-column: col-start / col-end;
                grid-row: row-start 3 / row-end 3;
            }
        }
        &__office-space{
            grid-column: col-full-start / col-full-end;
            grid-row: row-start 3 / row-end 3;

            @media screen and (max-width:600px){
                grid-column: col-start / col-end;
                grid-row: row-start 4 / row-end 4;
            }
        }
        &__business-support{
            grid-column: col-lg-start / col-lg-end;
            grid-row: row-start 4 / row-end 4;

            @media screen and (max-width:600px){
                grid-column: col-start / col-end;
                grid-row: row-start 5 / row-end 5;
            }
        }
        &__community{
            grid-column: col-sm-start / col-sm-end;
            grid-row: row-start 4 / row-end 4;

            @media screen and (max-width:600px){
                grid-column: col-start / col-end;
                grid-row: row-start 6 / row-end 6;
            }
        }
    }
</style>