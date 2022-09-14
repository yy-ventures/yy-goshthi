<template>
  <div class="experts">
    <div class="experts__heading-container">
      <div id="expert"></div>
      <div id="facilitator"></div>
    </div>
    <div class="experts__members">
      <div
        class="experts__members--member faded_out"
        v-for="expertsData in expertsDatas"
        :key="expertsData.id"
      >
        <div class="img-container">
          <div class="mask"></div>
          <img :src="`${expertsData.image}`" alt="image" />
        </div>
        <div class="content">
          <div class="content__info">
            <h4 class="content__info--name">{{ expertsData.name }}</h4>
            <span class="content__info--designation">{{
              expertsData.designation
            }}</span>
          </div>
          <a
            class="content__icon"
            target="_blank"
            rel="noopener noreferrer"
            :href="`${expertsData.linkedinLink}`"
            uk-icon="icon: linkedin; ratio: 1"
          ></a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import expertsDatas from "~/assets/data/experts_data.json";

import Axios from "axios";

// console.log("experts data: " + this.expertsDatas);

export default {
  data() {
    return {
      expertsDatas: [],
      pageY: null,
    };
  },
  mounted() {
    // API
    const response = Axios.get(
      "https://yyv.yyventures.org/api/get-experts-facilitators-data"
    ).then((res) => (this.expertsDatas = res.data.data));
    // console.log("expert & faciliators: " + this.expertsDatas);
    // console.log("expert & faciliators: " + expertsDatas);

    // console.log("experts data: " + this.expertsDatas);

    // ON SCROLL ANIMATION
    window.addEventListener("scroll", function () {
      let pageY = window.pageYOffset;
      const mediaQueryLargeDesktop = window.matchMedia("(min-width: 1920px)");
      const mediaQueryTab = window.matchMedia("(max-width: 960px)");
      const mediaQueryMob = window.matchMedia("(max-width: 600px)");
      const mediaQuerySmallMob = window.matchMedia("(max-width: 480px)");

      let expert = document.querySelector("#expert");
      let facilitator = document.querySelector("#facilitator");

      expert.style.backgroundPosition = `${pageY * 0.55 - 3500}px`;
      facilitator.style.backgroundPosition = `${-pageY * 0.55 + 4200}px`;

      if (mediaQueryLargeDesktop.matches) {
        expert.style.backgroundPosition = `${pageY * 0.55 - 3500}px`;
        facilitator.style.backgroundPosition = `${-pageY * 0.55 + 4550}px`;
      }
      if (mediaQueryTab.matches) {
        expert.style.backgroundPosition = `${pageY * 0.55 - 3900}px`;
        facilitator.style.backgroundPosition = `${-pageY * 0.55 + 4200}px`;
      }
      if (mediaQueryMob.matches) {
        expert.style.backgroundPosition = `${pageY * 0.55 - 3850}px`;
        facilitator.style.backgroundPosition = `${-pageY * 0.55 + 4000}px`;
      }
      if (mediaQuerySmallMob.matches) {
        expert.style.backgroundPosition = `${pageY * 0.55 - 3900}px`;
        facilitator.style.backgroundPosition = `${-pageY * 0.55 + 4000}px`;
      }
    });

    // console.log("expert & faciliators: " + expertsDatas);
  },
};
</script>

<style lang="scss" scoped>
.experts {
  margin: 80px 40px;
  overflow: hidden;

  display: flex;
  flex-direction: column;
  gap: 10px;

  @media screen and (max-width: 600px) {
    margin: 40px;
  }
  @media screen and (max-width: 480px) {
    margin: 40px 10px;
  }

  &__heading-container {
    background-color: #eaeceb;
    padding: 40px 0;

    #expert,
    #facilitator {
      background-repeat: no-repeat;
      background-size: contain;
      height: 110px;

      @media screen and (max-width: 600px) {
        height: 90px;
      }
      @media screen and (max-width: 480px) {
        height: 70px;
      }
      @media screen and (min-width: 1920px) {
        height: 135px;
      }
    }
    #expert {
      background-image: url("../../assets/images/landing-new-image/animated-text/experts.png");
      margin-bottom: 20px;
    }
    #facilitator {
      background-image: url("../../assets/images/landing-new-image/animated-text/facilitators.png");
    }
  }
  &__members {
    background-color: #eaeceb;
    padding: 80px 50px;

    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-gap: 60px 40px;

    @media screen and (min-width: 1301px) {
      grid-template-columns: repeat(3, minmax(250px, 1fr));
    }
    @media screen and (max-width: 960px) {
      padding: 80px 40px;
      grid-gap: 50px 20px;
    }
    @media screen and (max-width: 600px) {
      grid-template-columns: 1fr;
      padding: 80px 50px;
    }
    @media screen and (max-width: 480px) {
      padding: 40px 20px;
    }

    &--member {
      position: relative;

      transition: all 0.3s;

      &:hover {
        transform: scale(1.1);
      }

      .img-container {
        height: 400px;
        overflow: hidden;
        position: relative;

        @media screen and (max-width: 960px) {
          height: 300px;
        }

        @media screen and (max-width: 600px) {
          height: 450px;
        }
        @media screen and (min-width: 1920px) {
          height: 650px;
        }

        .mask {
          height: 100%;
          width: 100%;
          background-image: linear-gradient(
            transparent 70%,
            rgba(0, 0, 0, 0.6)
          );
          transition: all 0.3s;

          position: absolute;
        }
        img {
          height: 100%;
          width: 100%;
          object-fit: cover;
        }
      }
      .content {
        width: 100%;
        height: 100%;
        padding: 10px 20px;
        transition: all 0.3s;

        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 111;

        display: flex;
        justify-content: space-between;
        align-items: flex-end;

        @media screen and (max-width: 960px) {
          padding: 10px 10px;
        }
        @media screen and (max-width: 600px) {
          font-size: 10px;
          padding: 10px 40px;
        }
        @media screen and (max-width: 480px) {
          padding: 0;
        }

        &__info {
          @media screen and (max-width: 480px) {
            padding: 20px;
          }

          &--name {
            color: white !important;
            font-size: 20px;
            font-weight: 700;
            margin: 0;

            transition: all 0.3s;

            @media screen and (max-width: 960px) {
              font-size: 14px;
            }
            @media screen and (max-width: 600px) {
              font-size: 20px;
            }
          }
          &--designation {
            color: white;
            transition: all 0.3s;

            @media screen and (max-width: 960px) {
              font-size: 12px;
            }
          }
        }
        &__icon {
          color: white;
          border: 2px solid white;
          border-radius: 5px;

          visibility: hidden;

          transition-delay: 0.5s;
          transition: all 0.2s ease-out;
        }
      }
    }

    &--member:hover .mask {
      background-color: #0090bc6e;

      background-image: none;
    }
    &--member:hover .content {
      width: 80%;
      height: 80%;
      padding: 5px;

      border: 2px solid white;

      padding: 10px;
    }
    &--member:hover .content__info--name {
      font-size: 17px;
      line-height: 1.2;
      margin: 0;

      @media screen and (max-width: 960px) {
        font-size: 14px;
      }

      @media screen and (max-width: 600px) {
        font-size: 17px;
      }
    }
    &--member:hover .content__info--designation {
      font-size: 10px;
      line-height: 1.2;

      @media screen and (max-width: 960px) {
        font-size: 8px;
      }
      @media screen and (max-width: 600px) {
        font-size: 10px;
      }
    }

    &--member:hover .content__icon {
      visibility: visible;

      @media screen and (max-width: 960px) {
        height: 20px;
        width: 20px;
      }
      @media screen and (max-width: 600px) {
        height: 25px;
        width: 25px;
      }
    }
  }
}
</style>
