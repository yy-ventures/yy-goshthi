<template>
    <div class="experts">
        <div class="experts__heading-container">
            <div id="expert"></div>
            <div id="facilitator"></div>
        </div>
        <div class="experts__members">
            <div class="experts__members--member faded_out">
                <div class="img-container">
                    <div class="mask"></div>
                    <img src="../../assets/images/landing-new-image/members/tazin-shadid.png" alt="image">
                </div>
                <div class="content">
                    <div class="content__info">
                        <h4 class="content__info--name">Tazin Shadid</h4>
                        <span class="content__info--designation">Co-founder and CEO, AmarLab</span>
                    </div>
                    <a class="content__icon" target="_blank" rel="noopener noreferrer" href="https://www.linkedin.com/in/tazins/" uk-icon="icon: linkedin; ratio: 1"></a>
                </div>
            </div>
            <div class="experts__members--member faded_out">
                <div class="img-container">
                    <div class="mask"></div>
                    <img src="../../assets/images/landing-new-image/members/akkie-okma.png" alt="image">
                </div>
                <div class="content">
                    <div class="content__info">
                        <h4 class="content__info--name">Akkie Okma</h4>
                        <span class="content__info--designation">Technical Advisor, YY Ventures</span>
                    </div>
                    <a class="content__icon" target="_blank" rel="noopener noreferrer" href="https://www.linkedin.com/in/akkieokma/" uk-icon="icon: linkedin; ratio: 1"></a>
                </div>
            </div>
            <div class="experts__members--member faded_out">
                <div class="img-container">
                    <div class="mask"></div>
                    <img src="../../assets/images/landing-new-image/members/sabbir-amin.png" alt="image">
                </div>
                <div class="content">
                    <div class="content__info">
                        <h4 class="content__info--name">Sabbir Amin</h4>
                        <span class="content__info--designation">User-Centred Designer, Inked Studios</span>
                    </div>
                    <a class="content__icon" target="_blank" rel="noopener noreferrer" href="https://www.linkedin.com/in/sabbir-amin-848b275a/" uk-icon="icon: linkedin; ratio: 1"></a>
                </div>
            </div>
            <div class="experts__members--member faded_out">
                <div class="img-container">
                    <div class="mask"></div>
                    <img src="../../assets/images/landing-new-image/members/jacqueline-strayer.png" alt="image">
                </div>
                <div class="content">
                    <div class="content__info">
                        <h4 class="content__info--name">Prof Jacqueline Strayer</h4>
                        <span class="content__info--designation">Global Brand & Communications C-suite leader </span>
                    </div>
                    <a class="content__icon" target="_blank" rel="noopener noreferrer" href="https://www.linkedin.com/in/jfstrayer/" uk-icon="icon: linkedin; ratio: 1"></a>
                </div>
            </div>
            <div class="experts__members--member faded_out">
                <div class="img-container">
                    <div class="mask"></div>
                    <img src="../../assets/images/landing-new-image/members/shazeeb-khairul.png" alt="image">
                </div>
                <div class="content">
                    <div class="content__info">
                        <h4 class="content__info--name">Shazeeb M Khairul Islam</h4>
                        <span class="content__info--designation">Managing Director, YY Ventures</span>
                    </div>
                    <a class="content__icon" target="_blank" rel="noopener noreferrer" href="https://www.linkedin.com/in/shazeebislam/" uk-icon="icon: linkedin; ratio: 1"></a>
                </div>
            </div>
            <div class="experts__members--member faded_out">
                <div class="img-container">
                    <div class="mask"></div>
                    <img src="../../assets/images/landing-new-image/members/tanzin-shadid.png" alt="image">
                </div>
                <div class="content">
                    <div class="content__info">
                        <h4 class="content__info--name">Debojit Saha</h4>
                        <span class="content__info--designation">Managing Director, Kaizen CRS</span>
                    </div>
                    <a class="content__icon" target="_blank" rel="noopener noreferrer" href="https://www.linkedin.com/in/debojit-saha-434aa827/" uk-icon="icon: linkedin; ratio: 1"></a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                pageY: null,
            }
        },
        mounted() {
            window.addEventListener('scroll', function(){
                let pageY = window.pageYOffset;
                const mediaQueryTab = window.matchMedia('(max-width: 960px)');
                const mediaQueryMob = window.matchMedia('(max-width: 600px)');
                const mediaQuerySmallMob = window.matchMedia('(max-width: 480px)');

                let expert = document.querySelector('#expert');
                let facilitator = document.querySelector('#facilitator');

                expert.style.backgroundPosition = `${pageY * 0.55 - 3500}px`;
                facilitator.style.backgroundPosition = `${-pageY * 0.55 + 4200}px`;

                if(mediaQueryTab.matches) {
                    expert.style.backgroundPosition = `${pageY * 0.55 - 3900}px`;
                    facilitator.style.backgroundPosition = `${-pageY * 0.55 + 4200}px`;
                }
                if(mediaQueryMob.matches) {
                    expert.style.backgroundPosition = `${pageY * 0.55 - 3850}px`;
                    facilitator.style.backgroundPosition = `${-pageY * 0.55 + 4000}px`;
                }
                if(mediaQuerySmallMob.matches) {
                    expert.style.backgroundPosition = `${pageY * 0.55 - 3800}px`;
                    facilitator.style.backgroundPosition = `${-pageY * 0.55 + 3900}px`;
                }
                
            });
        },
    }
</script>

<style lang="scss" scoped>

    .experts{
        margin: 80px 40px;
        overflow: hidden;

        display: flex;
        flex-direction: column;
        gap: 10px;

        @media screen and (max-width: 600px){
            margin: 40px;
        }
        
        &__heading-container{

            background-color: #EAECEB;
            padding: 40px 0;            

            #expert, #facilitator{
                background-repeat: no-repeat;
                background-size: contain;
                height: 110px;

                @media screen and (max-width: 600px){
                    height: 90px;
                }
                @media screen and (max-width: 480px){
                    height: 70px;
                }
            }
            #expert{
                background-image: url('../../assets/images/landing-new-image/animated-text/experts.png');
                margin-bottom: 20px;
            }
            #facilitator{
                background-image: url('../../assets/images/landing-new-image/animated-text/facilitators.png');
            }
        }
        &__members{
            background-color: #EAECEB;
            padding: 80px 50px;

            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            grid-gap: 60px 40px;

            @media screen and (min-width: 1301px){
                grid-template-columns: repeat(3, minmax(250px, 1fr));
                
            }
            @media screen and (max-width: 960px){
                padding: 80px 40px;
                grid-gap: 50px 20px;
            }
            @media screen and (max-width: 600px){
                grid-template-columns: 1fr;
                padding: 80px 50px;
            }
            @media screen and (max-width: 480px){
                padding: 40px 20px;
            }

            &--member{
                position: relative;

                transition: all 0.3s;

                &:hover{
                    transform: scale(1.1);
                }

                .img-container{
                    height: 400px;
                    overflow: hidden;
                    position: relative;

                    @media screen and (max-width: 960px){
                        height: 300px;
                    }

                    @media screen and (max-width: 600px){
                        height: 450px;
                    }

                    .mask{
                        height: 100%;
                        width: 100%;
                        background-image: linear-gradient(transparent 70%, rgba(0, 0, 0, 0.6));
                        transition: all .3s;

                        position: absolute;

                    }
                    img{
                        height: 100%;
                        // width: 140%;
                        object-fit: cover;
                    }
                }
                .content{
                    width: 100%;
                    height: 100%;
                    padding: 10px 20px;
                    transition: all .3s;

                    position: absolute;
                    top: 50%;
                    left: 50%;
                    transform: translate(-50%, -50%);
                    z-index: 111;

                    display: flex;
                    justify-content: space-between;
                    align-items: flex-end;

                    @media screen and (max-width: 960px){
                        padding: 10px 10px;
                    }
                    @media screen and (max-width: 600px){
                        font-size: 10px;
                        padding: 10px 40px;
                    }
                    @media screen and (max-width: 480px){
                        padding: 0;
                    }

                    &__info{

                        @media screen and (max-width: 480px){
                            padding: 20px;
                        }
                        
                        &--name{
                            color: white !important;
                            font-size: 20px;
                            font-weight: 700;
                            margin: 0;

                            transition: all .3s;

                            @media screen and (max-width: 960px){
                                font-size: 14px;
                            }
                            @media screen and (max-width: 600px){
                                font-size: 20px;
                            }
                        }
                        &--designation{
                            color: white;
                            transition: all .3s;

                            @media screen and (max-width: 960px){
                                font-size: 12px;
                            }

                        }                        
                    }
                    &__icon{
                        color: white;
                        border: 2px solid white;
                        border-radius: 5px;

                        visibility: hidden;

                        transition-delay: .5s;
                        transition: all .2s ease-out;
                    }
                }

            }

            &--member:hover .mask{
                background-color: #0090bc6e;

                background-image: none;
            }
            &--member:hover .content{
                width: 80%;
                height: 80%;
                padding: 5px;

                border: 2px solid white;

                padding: 10px;
            }
            &--member:hover .content__info--name{
                font-size: 17px;
                line-height: 1.2;
                margin: 0;

                @media screen and (max-width: 960px){
                    font-size: 14px;
                }

                @media screen and (max-width: 600px){
                    font-size: 17px;
                }
            }
            &--member:hover .content__info--designation{
                font-size: 10px;
                line-height: 1.2;

                @media screen and (max-width: 960px){
                    font-size: 8px;
                }
                @media screen and (max-width: 600px){
                    font-size: 10px;
                }
            }

            &--member:hover .content__icon{
                visibility: visible;

                @media screen and (max-width: 960px){
                    height: 20px;
                    width: 20px;
                }
                @media screen and (max-width: 600px){
                    height: 25px;
                    width: 25px;
                }
            }

        }
    }

</style>