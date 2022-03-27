<template>
    <div class="footer">
        <div class="footer__yy-goshti">
            <img class='footer__yy-logo yy-goshthi-logo' src="../../../assets/images/landing-new-image/yyg-logo/yyg-logo.png" alt="">
            <p>YY Goshthi is a Social Business incubation program that helps socially & environmentally conscious entrepreneurs to launch their minimum viable product and raise the needed seed capital.</p>
        </div>
        <div class="footer__get-in-touch">
            <h4 class='footer__heading mb-1'>Get in Touch</h4>
            <p>info@yy.ventures</p>
            <p>9th floor, Grameen Telecom Bhaban, <br/>
                Mirpur 1, Dhaka 1216, Bangladesh.</p>
        </div>
        <div class="footer__follow-goshti">
            <h4 class='footer__heading mb-1'>Follow YY Goshthi</h4>
            <a href="https://www.facebook.com/yygoshti" target="_blank">Facebook</a>
            <a href="https://www.instagram.com/yygoshthi/" target="_blank">Instagram</a>
        </div>
        <div class="footer__powered">
            <h4 class='footer__heading'>Powered By</h4>
            <img class="footer__nea-logo" src="../../../assets/images/landing-new-image/yyg-logo/nea-logo.png" alt="">
            <p>Netherlands Enterprise Agency encourages entrepreneurs in sustainable, agrarian, innovative and international business. It helps with grants, finding business partners, know-how and compliance with laws and regulations.</p>
        </div>
        <div class="footer__created">
            <h4 class='footer__heading mb-1'>Created By</h4>
            <img class='footer__yy-logo' src="../../../assets/images/landing-new-image/yyg-logo/yyv-logo.png" alt="">
            <p>YY Ventures is an incubation and investment Social Business supporting early-stage entrepreneurs who are fighting carbon emission, poverty and unemployment.</p>
        </div>
        <div class="footer__follow-ventures">
            <h4 class='footer__heading mb-1'>Follow YY Ventures</h4>
            <a href="https://www.facebook.com/yyventures" target="_blank">Facebook</a>
            <a href="https://www.linkedin.com/company/yyventures" target="_blank">LinkedIn</a>
            <a href="https://www.instagram.com/yyventures/" target="_blank">Instagram</a>
            <a href="https://twitter.com/yyventures" target="_blank">Twitter</a>
        </div>
        <p>© 2022 · YY Ventures Limited · All Rights Reserved</p>
    </div>
</template>

<script>
    
</script>

<style lang="scss" scoped>
    .footer{
        padding: 50px 80px;
        background-color: #323637;
        color: white;

        display: grid;
        grid-template-columns: repeat(3, [col-start] minmax(250px, 1fr) [col-end]);
        grid-gap: 80px 60px;


        @media screen and (min-width: 1440px){
            padding: 50px 10%;
        }
        @media screen and (max-width: 800px){
            grid-template-columns: repeat(2, [col-start] minmax(250px, 1fr) [col-end]);
        }
        @media screen and (max-width: 600px){
            grid-template-columns: [col-start] 1fr [col-end];
            padding: 40px;
            grid-gap: 40px;
        }


        &__heading{
            font-weight: 700;
            color: white !important;
            
        }
        &__yy-logo{
            height: 40px;
            margin-bottom: 53px;
        }
        &__nea-logo{
            margin-left: -20px;
            height: 120px;
        }

        p{
            font-size: 14px;
            font-weight: 300;
        }
        a{
            font-size: 14px;
            font-weight: 300;
            display: block;
            color: white;
            text-decoration: none;
            border-bottom: 1px solid white;
            width: min-content;
            white-space: nowrap;

            &:not(:last-child){
                margin-bottom: 10px;
            }

            &:hover{
                color: #F6D04A;
                border-bottom: 1px solid #F6D04A;
            }

        }


        &__yy-goshti{
            .yy-goshthi-logo{
                margin-bottom: 15px;
            }
        }
        &__get-in-touch{

        }
        &__follow-goshti{

        }
        &__powered{

        }
        &__created{

        }
        &__follow-ventures{

        }
        .mb-1{
            margin-bottom: 45px;

            @media screen and (max-width: 600px){
                margin-bottom: 10px;
            }
        }

    }
</style>