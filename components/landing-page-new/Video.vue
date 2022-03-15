<template>
    <div class="video-section">
        <div class="video-section__main-video main-video-container">
            <iframe class="main-video" width="100%" height="100%" src="https://www.youtube.com/embed/Mv44JyiNS7w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
        <div class="video-section__video-group video-list-container">
            
            <div class="video-box list active">
                <div class="thumnail-contianer">
                    <img class="thumnail" src="../../assets/images/landing-new-image/video-thumnail/interview-thumbnails-broque.png" alt="">
                </div>
                <iframe class="list-video" width="150" height="100%" src="https://www.youtube.com/embed/Mv44JyiNS7w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <h3 class="video-box__title">Broqué | Spring 2020 Cohort</h3>
            </div>

            <div class="video-box list">
                <div class="thumnail-contianer">
                    <img class="thumnail" src="../../assets/images/landing-new-image/video-thumnail/interview-thumbnails-maxTapWater.png" alt="">
                </div>
                <iframe class="list-video" width="150" height="100%" src="https://www.youtube.com/embed/jLt07juKARY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <h3 class="video-box__title">Max TapWater | Spring 2020 Cohort</h3>
            </div>
            
            <div class="video-box list">
                <div class="thumnail-contianer">
                    <img class="thumnail" src="../../assets/images/landing-new-image/video-thumnail/interview-thumbnails-wizkit.png" alt="">
                </div>
                <iframe class="list-video" width="150" height="100%" src="https://www.youtube.com/embed/NJXyI9cBNek" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <h3 class="video-box__title">Wizkit | Fall 2020 Cohort</h3>
            </div>
            <div class="video-box list">
                <div class="thumnail-contianer">
                    <img class="thumnail" src="../../assets/images/landing-new-image/video-thumnail/interview-thumbnails-transEnd.png" alt="">
                </div>
                <iframe class="list-video" width="150" height="100%" src="https://www.youtube.com/embed/u0n5jkUuJOI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <h3 class="video-box__title">TransEnd | Fall 2020 Cohort</h3>
            </div>
        </div>
    </div>
</template>

<script>

    export default{
        mounted(){
            let videoList = document.querySelectorAll('.video-list-container .list');
        
            videoList.forEach(vid =>{
                console.log(vid);
                vid.onclick = () =>{
                    videoList.forEach(remove =>{remove.classList.remove('active')});
                    vid.classList.add('active');
                    let src = vid.querySelector('.list-video').src;
                    // let title = vid.querySelector('.list-title').innerHTML;
                    document.querySelector('.main-video-container .main-video').src = src;
                    document.querySelector('.main-video-container .main-video').play();
                    // document.querySelector('.main-video-container .main-vid-title').innerHTML = title;
        
                    console.log('I am clicked')
                };
            });

        }
    }
</script>

<style lang="scss">

    .video-section{
        height: min-content;
        padding: 50px 20px;
        background-color: #323637;
        overflow: hidden;
        margin: 80px 40px;

        display: grid;
        grid-template-columns: repeat(2, [col-start] 1fr [col-end]);
        grid-gap: 40px;

        @media screen and (max-width:600px){
            grid-template-columns: [col-start] 1fr [col-end];
            grid-template-rows: [row-start] min-content [row-end];
            grid-gap: 20px;
            margin: 40px;
        }
        @media screen and (max-width:480px){
            margin: 40px 10px;
        }

        &__main-video{
            grid-column: col-start 1 / col-end 1;


            background: #000;
            height: 400px;

            display: flex;
            align-items: center;
            justify-content: center;

            @media screen and (max-width: 1920px){
                
            }

            @media screen and (max-width:600px){
                grid-column: col-start / col-end;
                grid-row: row-start 1 / row-end 1;

                height: 300px;
            }
        }
        &__video-group{
            grid-column: col-start 2 / col-end 2;

            @media screen and (max-width:600px){
                grid-column: col-start / col-end;
                grid-row: row-start 2 / row-end 2;
            }
            
            
            height: 400px;
            padding: 20px 0;
            overflow-x: hidden;
            overflow-y: auto;
            border-top: 1px solid white;


            .video-box{
                height: 120px;
                padding: 10px 40px;
                display: flex;
                gap: 20px;
                cursor: pointer;

                .thumnail-contianer{
                    height: 100%;
                    width: 100px;

                    .thumnail{
                        height: 100%;
                        object-fit: cover;
                    }
                }

                .list-video{
                    display: none;
                }

                @media screen and (max-width: 600px){
                    padding: 10px;
                }

                &:hover{
                    background-color: rgba(0, 0, 0, 0.438);
                }

                &:not(:last-child){
                    margin-bottom: 10px;
                }

                @media screen and (max-width:600px){
                    height: 100px;
                }

                &__title{
                    font-size: 20px;
                    font-weight: 600;
                    margin: 0;
                    color: white;

                    @media screen and (max-width:600px){
                        font-size: 20px;
                    }
                    @media screen and (max-width:480px){
                        font-size: 16px;
                    }
                }
            }
        }
        .active{
            background-color: rgba(0, 0, 0, 0.438);
        }

    }
</style>