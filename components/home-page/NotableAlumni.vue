<template>
  <div class="notable-alumni">
    <div class="notable-alumni__heading-container">
      <div id="born"></div>
      <div id="entrepreneurs"></div>
    </div>
    <div class="notable-alumni__carousel-track faded_out">
      <!-- Garbagmen Slide -->
      <div
        :class="`notable-alumni__carousel-track__content ${alumniData.current}`"
        v-for="alumniData in alumniDatas"
        :key="alumniData.id"
      >
        <div class="notable-alumni__carousel-track__content--image">
          <img
            class="img"
            :src="`/_nuxt/assets/images/incubator/${alumniData.image}`"
            alt="alumni image"
          />
        </div>
        <div class="notable-alumni__carousel-track__content--info">
          <div class="text-container">
            <h3 class="text-container__heading">{{ alumniData.name }}</h3>
            <p class="text-container__details">{{ alumniData.description }}</p>
          </div>
          <div class="logo-container__social">
            <a
              target="_blank"
              rel="noopener noreferrer"
              :href="`${alumniData.facebookLink}`"
              uk-icon="icon: facebook; ratio: 1"
            ></a>
            <a
              target="_blank"
              rel="noopener noreferrer"
              :href="`${alumniData.twitterLink}`"
              uk-icon="icon: twitter; ratio: 1"
            ></a>
            <a
              target="_blank"
              rel="noopener noreferrer"
              :href="`${alumniData.linkedInLink}`"
              uk-icon="icon: linkedin; ratio: 1"
            ></a>
            <a
              target="_blank"
              rel="noopener noreferrer"
              :href="`${alumniData.instaLink}`"
              uk-icon="icon: instagram; ratio: 1"
            ></a>
          </div>
        </div>
      </div>
    </div>
    <!-- button -->
    <div class="slider-btn-container">
      <div
        class="notable-alumni__carousel-track__navigator-prev"
        @click="navigate_prev"
      >
        <img
          src="../../assets/images/landing-new-image/icon/left-arrow.png"
          alt="left arrow icon"
        />
      </div>
      <div
        class="notable-alumni__carousel-track__navigator-next"
        @click="navigate_next"
      >
        <img
          src="../../assets/images/landing-new-image/icon/right-arrow.png"
          alt="right arrow icon"
        />
      </div>
    </div>

    <!-- </div> -->
  </div>
</template>

<script>
import { dom } from "@/assets/scripts/dom_utils";
import alumniDatas from "@/assets/data/notable_alumni.json";

export default {
  data() {
    return {
      alumniDatas,
      pageY: null,
    };
  },
  mounted() {
    window.addEventListener("scroll", function () {
      let pageY = window.pageYOffset;
      const mediaQueryLargeDesktop = window.matchMedia("(min-width: 1920px)");
      const mediaQueryTab = window.matchMedia("(max-width: 960px)");
      const mediaQueryMob = window.matchMedia("(max-width: 600px)");
      const mediaQuerySmallMob = window.matchMedia("(max-width: 480px)");

      let born = document.querySelector("#born");
      let entrepreneurs = document.querySelector("#entrepreneurs");

      born.style.backgroundPosition = `${pageY * 0.55 - 2600}px`;
      entrepreneurs.style.backgroundPosition = `${-pageY * 0.55 + 3500}px`;

      if (mediaQueryLargeDesktop.matches) {
        born.style.backgroundPosition = `${pageY * 0.55 - 2550}px`;
        entrepreneurs.style.backgroundPosition = `${-pageY * 0.55 + 4000}px`;
      }
      if (mediaQueryTab.matches) {
        born.style.backgroundPosition = `${pageY * 0.55 - 3050}px`;
        entrepreneurs.style.backgroundPosition = `${-pageY * 0.55 + 3500}px`;
      }
      if (mediaQueryMob.matches) {
        born.style.backgroundPosition = `${pageY * 0.55 - 2900}px`;
        entrepreneurs.style.backgroundPosition = `${-pageY * 0.55 + 3200}px`;
      }
      if (mediaQuerySmallMob.matches) {
        born.style.backgroundPosition = `${pageY * 0.55 - 2950}px`;
        entrepreneurs.style.backgroundPosition = `${-pageY * 0.55 + 3050}px`;
      }
    });
  },
  methods: {
    navigate_next: () => {
      const slides = Object.values(
        dom(".notable-alumni__carousel-track").children
      );
      let current_index;
      slides.forEach((dom, index) => {
        if (dom.classList.contains("current")) current_index = index;
      });

      let next_index =
        current_index + 1 < slides.length
          ? current_index + 1
          : slides.length - 1;

      dom(".notable-alumni__carousel-track").style.transform =
        "translateX(-" + next_index * 100 + "%)";
      slides[current_index].classList.remove("current");
      slides[next_index].classList.add("current");
    },
    navigate_prev: () => {
      const slides = Object.values(
        dom(".notable-alumni__carousel-track").children
      );
      let current_index;
      slides.forEach((dom, index) => {
        if (dom.classList.contains("current")) current_index = index;
      });

      let prev_index = current_index - 1 < 0 ? 0 : current_index - 1;

      dom(".notable-alumni__carousel-track").style.transform =
        "translateX(-" + prev_index * 100 + "%)";
      slides[current_index].classList.remove("current");
      slides[prev_index].classList.add("current");
    },
  },
};
</script>

<style lang="scss" scoped>
.notable-alumni {
  margin: 80px 40px;
  overflow: hidden;

  display: flex;
  flex-direction: column;
  gap: 10px;

  position: relative;

  @media screen and (max-width: 600px) {
    margin: 40px;
  }
  @media screen and (max-width: 480px) {
    margin: 40px 10px;
  }

  &__heading-container {
    background-color: #eaeceb;
    padding: 40px 0;

    #born,
    #entrepreneurs {
      background-repeat: no-repeat;
      background-size: contain;
      height: 80px;
      @media screen and (max-width: 600px) {
        height: 60px;
      }
      @media screen and (max-width: 480px) {
        height: 50px;
      }
      @media screen and (min-width: 1920px) {
        height: 100px;
      }
    }
    #born {
      background-image: url("../../assets/images/landing-new-image/animated-text/title-2.png");
      margin-bottom: 20px;
    }
    #entrepreneurs {
      background-image: url("../../assets/images/landing-new-image/animated-text/title-1.png");
    }
  }
  &__carousel-track {
    transition: transform 1s;
    display: flex;

    &__content {
      background-color: #eaeceb;
      flex: 0 0 100%;
      padding: 40px;

      display: grid;
      grid-template-columns: repeat(2, [col-start] 1fr [col-end]);
      grid-template-rows: min-content;
      grid-gap: 70px;

      @media screen and (max-width: 600px) {
        grid-template-columns: [col-start] 1fr [col-end];
        grid-template-rows: repeat(2, [row-start] min-content [row-end]);
        grid-gap: 30px;

        padding: 0;
      }

      &--image {
        grid-column: col-start 1 / col-end 1;
        height: 450px;

        @media screen and (max-width: 600px) {
          grid-column: col-start / col-end;
          grid-row: row-start 1 / row-end 1;

          height: 400px;
        }

        @media screen and (max-width: 480px) {
          height: 300px;
        }
        @media screen and (min-width: 1920px) {
          height: 600px;
        }

        .img {
          height: 100%;
          object-fit: cover;

          @media screen and (min-width: 1920px) {
            width: 100%;
          }
        }
      }
      &--info {
        grid-column: col-start 2 / col-end 2;

        @media screen and (max-width: 600px) {
          grid-column: col-start / col-end;
          grid-row: row-start 2 / row-end 2;

          padding: 0 1rem 1rem 1rem;
        }

        .logo-container {
          &__social {
            align-self: flex-end;

            a:not(:last-child) {
              margin-right: 10px;
            }
          }
        }

        .text-container {
          &__heading {
            font-size: 30px;
            font-weight: 900;
            color: #323637;

            @media screen and (max-width: 600px) {
              font-size: 22px;
            }
          }
          &__details {
            color: #323637;

            @media screen and (max-width: 600px) {
              font-size: 14px;
            }
          }
        }
      }
    }
    &__navigator-next,
    &__navigator-prev {
      background-color: #323637;
      border: none;
      height: 30px;
      width: 30px;
      border-radius: 50%;
      cursor: pointer;

      display: flex;
      align-items: center;
      justify-content: center;

      svg {
        polyline {
          stroke: #f2f2f2;
        }
      }
    }
  }

  .slider-btn-container {
    position: absolute;
    bottom: 60px;
    right: 60px;
    z-index: 999;

    display: flex;
    gap: 20px;

    @media screen and (max-width: 600px) {
      bottom: 20px;
    }
  }
}
</style>
