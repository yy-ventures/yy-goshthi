<template>
    <div class="success-popup">
        <div class="success-popup__container">
            <div class="success-popup__container--heading">
                <span>Application successful!</span>
                <div class="icon-container">
                    <img src="../../../assets/images/landing-new-image/icon/successful-icon.jpg" alt="success icon">
                </div>
            </div>
            <p>Thank you for submitting your application for the YY Goshthi Incubation Program Spring 2022 Cohort.</p>
            <br/>
            <p>We have sent you a confirmation email. If you haven't received any confirmation email, please email <a href="mailto:mazbah@yy.ventures" target="_blank">mazbah@yy.ventures</a> or contact +8801797332722</p>
            <a href="/" class="btn">Done</a>
        </div>
    </div>
</template>

<script>

</script>

<style lang="scss">
    .success-popup{
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: rgba(0, 0, 0, 0.5);
        &__container{
            position: sticky;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            padding: 20px 40px;
            background-color: white;
            width: 500px;

            @media screen and (max-width: 600px){
                width: 350px;
                transform: translate(-7%, -50%);
            }
            &--heading{
                display: flex;
                align-items: center;
                justify-content: center;
                gap: 20px;
                margin-bottom: 20px;
                span{
                    display: block;
                    font-size: 24px;
                    font-weight: 700;

                    @media screen and (max-width: 600px){
                        font-size: 16px;
                    }
                }
                .icon-container{
                    height: 30px;

                    img{
                        height: 100%;
                        object-fit: contain;
                    }
                }
            }
            p{
                @media screen and (max-width: 600px){
                    font-size: 13px;
                }
            }
            .btn{
                display: block;
                width: max-content;
                padding: 8px 30px;
                color: white;
                background-color: #1e87f0;
                font-size: 16px;
                text-decoration: none;
                border-radius: 5px;
                margin: 50px auto 0 auto;
                transition: all .3s;

                @media screen and (max-width: 600px){
                    padding: 6px 25px;
                    font-size: 13px;
                }
                
                &:hover{
                    background-color: #1e87f0e7;
                }
            }
        }
    }
</style>