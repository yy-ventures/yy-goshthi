<template>
  <div class="eligibility">
    <div class="eligibility__heading-container">
      <h1>Eligibility</h1>
    </div>
    <div class="eligibility__box-container">
      <div class="eligibility__box-container--box-1 box faded_out">
        <h2 class="heading-1">The legal status of business</h2>
        <p>
          The program has primarily been designed for the needs of Social
          Businesses; however, non-profits, for-profits, co-operatives, and
          community contribution businesses are all eligible as long as they
          serve a crucial social or environmental cause and are willing to
          incorporate a Social Business model moving forward.
        </p>
      </div>
      <div class="eligibility__box-container--box-2 box faded_out">
        <h2 class="heading-2">Stage of venture</h2>
        <p>
          The program is geared towards those at an early-stage of development,
          who have an idea they are willing to invest in. Ideally, applicants
          have completed some measure of feasibility assessment and can see
          themselves moving to launch in 4-6 months. Those who have already
          launched but need support to refine their business plan and scale up
          operations are also encouraged to apply.
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.eligibility {
  margin: 80px 40px;
  overflow: hidden;

  @media screen and (max-width: 600px) {
    margin: 40px;
  }
  @media screen and (max-width: 480px) {
    margin: 40px 10px;
  }

  &__heading-container {
    text-align: center;

    h1 {
      font-size: calc(60px + 2vw);
      color: transparent !important;
      -webkit-text-stroke-width: 2px;
      -webkit-text-stroke-color: #323637;
      @media screen and (max-width: 960px) {
        font-size: calc(50px + 2vw);
      }
    }
  }
  &__box-container {
    display: grid;
    grid-template-columns: repeat(2, [col-start] 1fr [col-end]);
    grid-gap: 10px;

    @media screen and (max-width: 600px) {
      grid-template-columns: [col-start] 1fr [col-end];
    }

    .box {
      background-color: #323637;
      color: white;
      padding: 40px 20px;

      .heading-1,
      .heading-2 {
        font-size: 60px;
        font-weight: 900;
        color: #d0d2d3;

        @media screen and (max-width: 600px) {
          font-size: 40px;
        }
        @media screen and (max-width: 375px) {
          font-size: 30px;
        }
      }
      .heading-1 {
        margin-bottom: 40px;
      }
      .heading-2 {
        margin-bottom: 110px;

        @media screen and (max-width: 600px) {
          margin-bottom: 40px;
        }
        @media screen and (min-width: 1920px) {
          margin-bottom: 40px;
        }
      }

      p {
        font-size: 14;
        font-weight: 300;
        line-height: 1.2;
      }
    }

    &--box-1 {
      grid-column: col-start 1 / col-end 1;

      @media screen and (max-width: 600px) {
        grid-column: col-start / col-end;
      }
    }
    &--box-2 {
      grid-column: col-start 2 / col-end 2;

      @media screen and (max-width: 600px) {
        grid-column: col-start / col-end;
      }
    }
  }
}
</style>
