<template>
  <div class="impact-section">
    <div class="layer">
      <div class="impact-section__heading-container">
        <div id="our"></div>
        <div id="impact-text"></div>
      </div>
      <div class="impact-section__info">
        <div class="box box-one">
          <h3 class="number">63%</h3>
          <span class="text">Female-led Businesses</span>
        </div>
        <div class="box box-two">
          <h3 class="number">11</h3>
          <span class="text">Programs Delivered</span>
        </div>
        <div class="box box-three">
          <h3 class="number">150633</h3>
          <span class="text">Lives Impacted</span>
        </div>
        <div class="box box-four">
          <h3 class="number">1372</h3>
          <span class="text">Jobs Created</span>
        </div>
        <div class="box box-five">
          <h3 class="number">64</h3>
          <span class="text">Entrepreneurs Supported</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
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

      let our = document.querySelector("#our");
      let impactText = document.querySelector("#impact-text");

      our.style.backgroundPosition = `${pageY * 0.7 - 700}px`;
      impactText.style.backgroundPosition = `${-pageY * 0.55 + 1300}px`;

      if (mediaQueryLargeDesktop.matches) {
        our.style.backgroundPosition = `${pageY * 0.7 - 700}px`;
        impactText.style.backgroundPosition = `${-pageY * 0.7 + 1900}px`;
      }
      if (mediaQueryTab.matches) {
        our.style.backgroundPosition = `${pageY * 0.7 - 800}px`;
        impactText.style.backgroundPosition = `${-pageY * 0.7 + 1250}px`;
      }
      if (mediaQueryMob.matches) {
        our.style.backgroundPosition = `${pageY * 0.7 - 1000}px`;
        impactText.style.backgroundPosition = `${-pageY * 0.7 + 1250}px`;
      }
      if (mediaQuerySmallMob.matches) {
        our.style.backgroundPosition = `${pageY * 0.7 - 1100}px`;
        impactText.style.backgroundPosition = `${-pageY * 0.7 + 1300}px`;
      }
    });

    // counting --------->
    // const counters = document.querySelectorAll('.number');
    // const speed = 500;

    // counters.forEach((counter) => {
    //     const updateCount = () => {
    //         const target = parseInt(counter.getAttribute('data-target'));
    //         const count = parseInt(counter.innerText);
    //         const increment = Math.trunc(target / speed);

    //         if (count < target) {
    //         counter.innerText = count + increment;
    //         setTimeout(updateCount, 1);
    //         } else {
    //         counter.innerText = target;
    //         }
    //     };
    //     updateCount();
    // });
  },
};
</script>

<style lang="scss" scoped>
.impact-section {
  background-image: url("../../assets/images/landing-new-image/background-image/our-impact-bg.jpg");
  background-size: cover;
  background-position: center;

  height: 700px;
  margin: 80px 40px;
  position: relative;

  @media screen and (max-width: 600px) {
    margin: 40px;
    height: 600px;
  }
  @media screen and (max-width: 480px) {
    margin: 40px 10px;
  }

  .layer {
    background-color: rgba(0, 0, 0, 0.6);
    padding: 4rem 6rem;

    @media screen and (max-width: 600px) {
      padding: 2rem 0;
    }

    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    gap: 2rem;
  }

  &__heading-container {
    width: 100%;

    #our,
    #impact-text {
      background-repeat: no-repeat;
      background-size: contain;
      height: 100px;

      @media screen and (max-width: 600px) {
        height: 70px;
      }
      @media screen and (min-width: 1920px) {
        height: 130px;
      }
    }
    #our {
      background-image: url("../../assets/images/landing-new-image/animated-text/text-our.png");
      margin-bottom: 20px;
    }
    #impact-text {
      background-image: url("../../assets/images/landing-new-image/animated-text/text-impact.png");
    }
  }

  &__info {
    width: 100%;

    display: grid;
    grid-template-columns: repeat(5, [col-start] 1fr [col-end]);
    grid-template-rows: repeat(2, [row-start] min-content [row-end]);

    @media screen and (max-width: 1100px) {
      grid-template-columns:
        [col-full-start] repeat(2, [col-start] 1fr [col-end])
        [col-full-end];
      grid-template-rows: repeat(3, [row-start] min-content [row-end]);
    }

    .box-one {
      grid-column: col-start 2 / col-end 2;
      grid-row: row-start 1 / row-end 1;

      @media screen and (max-width: 1100px) {
        grid-column: col-start 1 / col-end 1;
        grid-row: row-start 1 / row-end 1;
      }
    }
    .box-two {
      grid-column: col-start 4 / col-end 4;
      grid-row: row-start 1 / row-end 1;

      @media screen and (max-width: 1100px) {
        grid-column: col-start 2 / col-end 2;
        grid-row: row-start 1 / row-end 1;
      }
    }
    .box-three {
      grid-column: col-start 1 / col-end 1;
      grid-row: row-start 2 / row-end 2;

      @media screen and (max-width: 1100px) {
        grid-column: col-start 1 / col-end 1;
        grid-row: row-start 2 / row-end 2;
      }
    }
    .box-four {
      grid-column: col-start 3 / col-end 3;
      grid-row: row-start 2 / row-end 2;

      @media screen and (max-width: 1100px) {
        grid-column: col-start 2 / col-end 2;
        grid-row: row-start 2 / row-end 2;
      }
    }
    .box-five {
      grid-column: col-start 5 / col-end 5;
      grid-row: row-start 2 / row-end 2;

      @media screen and (max-width: 1100px) {
        grid-column: col-full-start / col-full-end;
        grid-row: row-start 3 / row-end 3;
      }
    }

    .box {
      display: flex;
      flex-direction: column;
      align-items: center;

      @media screen and (max-width: 1100px) {
        &:not(:last-child) {
          margin-bottom: 20px;
        }
      }

      .number {
        color: white;
        font-size: calc(40px + 2vw);
        font-weight: 900;
        margin: 0 !important;

        @media screen and (max-width: 1300px) {
          font-size: calc(25px + 2vw);
        }

        @media screen and (max-width: 600px) {
          font-size: calc(30px + 2vw);
        }
      }
      .text {
        color: white;
        font-size: 18px;
        font-weight: 600;
        white-space: nowrap;
        // text-align: center;

        @media screen and (max-width: 600px) {
          font-size: 16px;
        }
      }
    }
  }
}
</style>
