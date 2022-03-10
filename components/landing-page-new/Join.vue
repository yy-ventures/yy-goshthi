<template>
    <div class="join">
        <h1 class="text text-stroke">Got</h1>
        <h1 class="text text-lg-space">A Social Business?</h1>
        <h1 class="join-text highlight">JOIN</h1>
        <p class="dhaka-text">OUR INCUBATOR IN DHAKA</p>
        <span class="yyg-application">YY Goshthi Spring 2022 cohort application will open in March 2022</span>
    </div>
</template>

<script>
    
</script>

<style lang="scss">
    .join{
        text-align: center;
        padding: 20px;
        
        @media screen and (max-width: 600px){
            padding: 0;
            margin: 40px;
        }
        
        .text{
            font-size: calc(40px + 1vw);
            color: #323637;
            white-space: nowrap;
            margin: 0;

            @media screen and (max-width:600px){
                // display: flex;
                // justify-content: center;
                // width: 100%;
                font-size: calc(35px + 1vw);
            }
            
        }
        .text-stroke{
            color: transparent !important;
            -webkit-text-stroke-width: 1px;
            -webkit-text-stroke-color: #323637;

            @media screen and (max-width:600px){
                // margin-left: 0;
            }
        }
        .text-lg-space{
            margin-bottom: 50px;

            @media screen and (max-width:600px){
                margin-bottom: 50px;
            }
        }
        .join-text{
            font-size: calc(50px + 2vw);
            margin: 0;

            @media screen and (max-width:600px){
                font-size: calc(40px + 2vw);
            }
        }
        .dhaka-text{
            color: #323637;
            font-size: calc(8px + 1vw);
            margin: 0 0 40px 0;

            @media screen and (max-width:600px){
                margin: 0 0 40px 0;
            }
        }

        .yyg-application{
            font-size: calc(8px + 1vw);
            font-weight: 900;
            color: #C82159;

            @media screen and (max-width: 600px){
                font-size: calc(12px + 1vw);
            }
        }
    }
</style>