<template>
  <div class="programs-team">
    <div class="programs-team__heading-container">
      <div id="programs"></div>
      <div id="team"></div>
    </div>
    <div class="programs-team__members">
      <!-- <div class="programs-team__members--member faded_out">
                <div class="img-container">
                    <div class="mask"></div>
                    <img src="../../assets/images/landing-new-image/members/sharika.webp" alt="image">
                </div>
                <div class="content">
                    <div class="content__info">
                        <h4 class="content__info--name">Sharika Sadaf</h4>
                        <span class="content__info--designation">Head of Program & Partnerships</span>
                    </div>
                    <a class="content__icon" target="_blank" rel="noopener noreferrer" href="https://www.linkedin.com/in/sharikasadaf/" uk-icon="icon: linkedin; ratio: 1"></a>
                </div>
            </div> -->
      <div class="programs-team__members--member faded_out">
        <div class="img-container">
          <div class="mask"></div>
          <img
            class="img-mazbah"
            src="../../assets/images/landing-new-image/members/mazbah.png"
            alt="image"
          />
        </div>
        <div class="content">
          <div class="content__info">
            <h4 class="content__info--name">Mazbahul Islam</h4>
            <span class="content__info--designation">Program Manager</span>
          </div>
          <a
            class="content__icon"
            target="_blank"
            rel="noopener noreferrer"
            href="https://www.linkedin.com/in/mazbahnow/"
            uk-icon="icon: linkedin; ratio: 1"
          ></a>
        </div>
      </div>
      <div class="programs-team__members--member faded_out">
        <div class="img-container">
          <div class="mask"></div>
          <img
            src="../../assets/images/landing-new-image/members/maisha.webp"
            alt="image"
          />
        </div>
        <div class="content">
          <div class="content__info">
            <h4 class="content__info--name">Maisha Ahmed</h4>
            <span class="content__info--designation"
              >Deputy Program Manager</span
            >
          </div>
          <a
            class="content__icon"
            target="_blank"
            rel="noopener noreferrer"
            href="https://www.linkedin.com/in/maisha-ahmed-nandita-892792134/"
            uk-icon="icon: linkedin; ratio: 1"
          ></a>
        </div>
      </div>
    </div>
    <a href="https://yy.ventures/about#staff" target="_blank" class="btn"
      >See Full Team
      <img
        class="btn__icon"
        src="../../assets/images/landing-new-image/icon/right-arrow.svg"
        alt="right arrow"
    /></a>
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

      let programs = document.querySelector("#programs");
      let team = document.querySelector("#team");

      programs.style.backgroundPosition = `${pageY * 0.55 - 4300}px`;
      team.style.backgroundPosition = `${-pageY * 0.55 + 5100}px`;

      if (mediaQueryLargeDesktop.matches) {
        programs.style.backgroundPosition = `${pageY * 0.55 - 4500}px`;
        team.style.backgroundPosition = `${-pageY * 0.55 + 5800}px`;
      }
      if (mediaQueryTab.matches) {
        programs.style.backgroundPosition = `${pageY * 0.55 - 4500}px`;
        team.style.backgroundPosition = `${-pageY * 0.55 + 5000}px`;
      }
      if (mediaQueryMob.matches) {
        programs.style.backgroundPosition = `${pageY * 0.55 - 5800}px`;
        team.style.backgroundPosition = `${-pageY * 0.55 + 6100}px`;
      }
      if (mediaQuerySmallMob.matches) {
        programs.style.backgroundPosition = `${pageY * 0.55 - 5750}px`;
        team.style.backgroundPosition = `${-pageY * 0.55 + 5900}px`;
      }
    });
  },
};
</script>

<style lang="scss" scoped>
.programs-team {
  margin: 80px 40px;
  overflow: hidden;
  background-color: #3a3b3a;

  @media screen and (max-width: 480px) {
    margin: 40px 10px;
  }

  &__heading-container {
    padding: 40px 0;

    @media screen and (max-width: 600px) {
      padding-bottom: 0;
    }

    #programs,
    #team {
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
        height: 130px;
      }
    }
    #programs {
      background-image: url("../../assets/images/landing-new-image/animated-text/programs.png");
      margin-bottom: 20px;
    }
    #team {
      background-image: url("../../assets/images/landing-new-image/animated-text/team.png");
    }
  }

  &__members {
    padding: 80px 50px;

    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-gap: 60px 40px;

    @media screen and (min-width: 1301px) {
      grid-template-columns: repeat(2, minmax(250px, 450px));
      justify-content: center;
    }
    @media screen and (min-width: 1920px) {
      grid-template-columns: repeat(2, minmax(250px, 550px));
      justify-content: center;
    }
    @media screen and (max-width: 1300px) {
      grid-template-columns: repeat(2, minmax(250px, 350px));
      justify-content: center;
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
        height: 500px;
        overflow: hidden;
        position: relative;
        background-color: white;

        @media screen and (max-width: 960px) {
          height: 400px;
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
            transparent 75%,
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
        .img-mazbah {
          margin-top: 2rem;
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

        &__info {
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
          width: max-content;

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

  .btn {
    font-size: 20px;
    width: max-content;
    white-space: nowrap;
    text-decoration: none;
    color: #0b9bbf;
    padding: 5px 15px;
    border: 1px solid white;
    background-color: transparent;
    margin: 0 auto 80px auto;
    cursor: pointer;

    display: flex;
    align-items: center;
    gap: 10px;

    @media screen and (max-width: 600px) {
      font-size: 16px;
    }

    &__icon {
      height: 20px;

      transition: all 0.2s;

      @media screen and (max-width: 600px) {
        height: 16px;
      }
    }

    &:hover .btn__icon {
      margin-left: 7px;
    }
  }
}
</style>
