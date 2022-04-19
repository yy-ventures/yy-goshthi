<template>
    <div class="draft-success-popup">
        <div class="draft-success-popup__container">
            <div class="draft-success-popup__container--heading">
                <span>Save as draft successful!</span>
                <div class="icon-container">
                    <img src="../../../assets/images/landing-new-image/icon/successful-icon.jpg" alt="success icon">
                </div>
            </div>
            <!-- <p>Please look for your User ID and Password in your email.<br/>You must login to continue your registration. <span class="login-data">User ID: {{appId}} {{email1}}</span> <span class="login-data">Password: {{password}} {{email2}}</span></p> -->
            <p>To come back to your application, please login with the following User ID and Password:</p>
            <span class="login-data">User ID: {{appId}}</span>
            <span class="login-data">Password: {{password}}</span>
            <p>We have also sent the login credentials to your email address at:</p>
            <span class="login-data">{{email1}}</span>
            <span class="login-data">{{email2}}</span>
            <div class="btn-container">
                <a href="/" class="btn">Done</a>
                <a href="/login" class="btn">Login</a>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        props:{
            appId: String,
            password: String,
            email1: '',
            email2: ''
        }
    }
</script>

<style lang="scss">
    .draft-success-popup{
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
                // .login-data{
                //     display: block;
                //     color: #1e87f0;
                // }
            }
            .login-data{
                    display: block;
                    font-size: 16px;
                    font-weight: 700;
                    color: #1e87f0;

                    @media screen and (max-width: 600px){
                        font-size: 16px;
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
            .btn-container{
                display: flex;
                justify-content: space-between;
                padding-inline: 20px;
            }
        }
    }
</style>