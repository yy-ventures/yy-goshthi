<template>
  <div id="home-hero">
    <div class="uk-cover-container" uk-height-viewport="min-height: 450">
      <!-- <img src="~assets/svg/home-hero-bg.svg" alt="" uk-cover /> -->
      <!--       <img src="images/home/01.jpg" alt="" uk-cover />
      <img src="images/home/02.jpg" alt="" uk-cover />
      <img src="images/home/03.jpg" alt="" uk-cover />
      <img src="images/home/04.jpg" alt="" uk-cover />
      <img src="images/home/05.jpg" alt="" uk-cover />
      <img src="images/home/06.jpg" alt="" uk-cover />
      <img src="images/home/07.jpg" alt="" uk-cover /> -->
      <!-- <img
        v-for="(item, index) in slides"
        :src="item"
        :key="index"
        alt=""
        uk-cover
        class="invisible-slide"
        :class="{ 'visible-slide': isVisible(index) }"
      /> -->

      <div
        class="uk-visible-toggle uk-light uk-visible@l"
        tabindex="-1"
        uk-slideshow=" autoplay: true; autoplay-interval:1000; animation:fade;"
      >
        <ul class="uk-slideshow-items">
          <li v-for="(image, index) in slides" :key="index">
            <img :src="image" alt="" uk-cover />
          </li>
        </ul>
      </div>

      <div class="uk-container hero-container uk-position-cover">
        <div class="hero-text-container uk-position-center-left">
          <!-- <h1 class="">                                                                       -->
          <!--   <span>Incubating and</span>                                                       -->
          <!--   <span>Investing in</span>                                                         -->
          <!--   <span class="background-accent"                                                   -->
          <!--     ><span                                                                          -->
          <!--       class="inner-span"                                                            -->
          <!--       uk-scrollspy="cls:inner-span-animate; hidden:false;  delay:1000; repeat:true" -->
          <!--       >Social Businesss</span                                                       -->
          <!--     ></span                                                                         -->
          <!--   >                                                                                 -->
          <!-- </h1>                                                                               -->

          <h1 class="heading">Together We Are</h1>
          <h1 class="write">&nbsp;</h1>
          <!-- <h2>YY Goshthi Fall 2021 Cohort Application is closed.</h2> -->
          <!-- <a href="https://airtable.com/shraT8HKyxXMuaG6X" class="link_button">Apply Now</a> -->

          <!-- <span class="yyg-application">Application for Spring 2022 cohort is open now</span>
          <a href="https://incubator.yy.ventures/application/" target="_blank" class="btn">Apply</a> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentSlide: "images/home/01.svg",
      count: 0,
      slides: [
        "images/home/01.svg",
        "images/home/02.svg",
        "images/home/03.svg",
        "images/home/04.svg",
        "images/home/05.svg",
        "images/home/06.svg",
      ],
      slidesJpg: [
        "images/home/01.jpg",
        "images/home/02.jpg",
        "images/home/03.jpg",
        "images/home/05.jpg",
        "images/home/06.jpg",
        "images/home/07.jpg",
      ],
      animation: "uk-animation-fade",
    };
  },
  methods: {
    changeSlide() {
      this.count++;
      //this.count = Math.floor(Math.random() * 6)

      if (this.count >= 6) this.count = 0;
      setTimeout(() => {
        this.changeSlide();
      }, 2000);
    },
    isVisible(index) {
      if (index == this.count) return true;
      else return false;
    },
  },
  mounted() {
    //this.changeSlide()
  },
};
</script>

<style lang="less" scoped>
#home-hero {
  .invisible-slide {
    position: absolute;
    opacity: 0;
    transition: opacity 1000ms linear;
  }
  .visible-slide {
    position: static;
    opacity: 100;
  }
  //background-image: url('~assets/svg/home-hero-bg.svg');
  background-position: right;
  .hero-container {
    padding-top: 15%;
    padding-bottom: 15%;

    @media screen and (max-width: 600px) {
      margin-top: 20px;
    }
  }
  .hero-text-container {
    span {
      display: block;
    }
    .inner-span {
      display: inline;
      position: relative;
      overflow: hidden;
      &::after {
        content: "";
        position: absolute;
        z-index: -1;
        right: 0;
        width: 0;
        bottom: 10px;
        background: #efd30a;
        height: 25px;
        transition-property: width;
        transition-duration: 1s;
        transition-timing-function: ease-in;
        @media @small-down {
          bottom: 0px;
        }
      }
    }
    .inner-span-animate {
      &::after {
        left: 0;
        right: auto;
        width: 100%;
      }
    }
    img {
      max-width: 100px;
    }
    padding-left: 40px;
    h1 {
      /* margin-top: 10px; */
      color: #3a3b3a;
      font-size: 80px !important;
      line-height: 1.1 !important;
      text-transform: none !important;

      @media (max-width: 600px) {
        font-size: 40px !important;
      }

      // @media(max-width: 480px){
      //   font-size: 65px !important;
      // }
      /* margin-bottom: -45px; */
      @media @tablet-down {
        // font-size: 80px !important;
        /* margin-bottom: -35px; */
      }
      @media @small-down {
        // font-size: 80px !important;
      }
      @media (min-width: 601px) {
        /* font-size: 100px !important; */
      }
    }
  }

  .btn {
    font-size: 20px;
    width: max-content;
    white-space: nowrap;
    text-decoration: none;
    color: white;
    background-color: #0b9bbf;
    padding: 0px 40px;
    border: 2px solid #0b9bbf;
    // background-color: transparent;
    // margin: 20px auto;
    margin-top: 10px;
    cursor: pointer;
    font-family: sans-serif;

    display: flex;
    align-items: center;
    gap: 10px;

    @media screen and (max-width: 600px) {
      font-size: 16px;
    }
  }
  .yyg-application {
    font-size: 30px;
    font-weight: 700;
    color: #0b9bbf;
  }
}
</style>
