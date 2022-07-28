<template>
  <div class="join">
    <h1 class="text text-stroke">Got An Early Stage</h1>
    <h1 class="text text-lg-space">Social Business?</h1>
    <h1 class="join-text highlight">JOIN</h1>
    <p class="dhaka-text">OUR INCUBATION PROGRAM IN DHAKA</p>
    <span class="yyg-application"
      >Application for Fall 2022 cohort will open soon</span
    >
    <!-- <a href="https://incubator.yy.ventures/application/" target="_blank" class="btn">Apply</a>
        <span class="yyg-application-1">Application closes on 4th June, 2022</span> -->
  </div>
</template>

<script></script>

<style lang="scss">
.join {
  text-align: center;
  padding: 20px 20px 100px 20px;

  @media screen and (max-width: 600px) {
    padding: 0;
    margin: 40px;
  }
  @media screen and (max-width: 480px) {
    margin: 40 10pxpx;
  }

  .text {
    font-size: calc(40px + 1vw);
    color: #323637;
    white-space: nowrap;
    margin: 0;

    @media screen and (max-width: 600px) {
      font-size: calc(35px + 1vw);
    }
  }
  .text-stroke {
    color: transparent !important;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #323637;

    @media screen and (max-width: 600px) {
      white-space: pre-wrap;
    }
  }
  .text-lg-space {
    margin-bottom: 50px;
    white-space: pre-wrap;

    @media screen and (max-width: 600px) {
      margin-bottom: 50px;
    }
  }
  .join-text {
    font-size: calc(50px + 2vw);
    margin: 0;

    @media screen and (max-width: 600px) {
      font-size: calc(40px + 2vw);
    }
  }
  .dhaka-text {
    color: #323637;
    font-size: calc(8px + 1vw);
    margin: 0 0 40px 0;

    @media screen and (max-width: 600px) {
      margin: 0 0 40px 0;
    }
  }

  .yyg-application {
    font-size: calc(8px + 1vw);
    font-weight: 900;
    color: #0b9bbf;

    @media screen and (max-width: 600px) {
      font-size: calc(12px + 1vw);
    }
  }
  .yyg-application-1 {
    font-size: calc(8px + 1vw);
    font-weight: 300;
    color: #000;
    font-family: sans-serif;

    @media screen and (max-width: 600px) {
      font-size: calc(12px + 1vw);
    }
  }

  .btn {
    font-size: 20px;
    width: max-content;
    white-space: nowrap;
    text-decoration: none;
    color: #0b9bbf;
    padding: 0px 40px;
    border: 2px solid #323637;
    background-color: transparent;
    margin: 20px auto;
    cursor: pointer;
    font-family: sans-serif;

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
