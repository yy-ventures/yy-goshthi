<template>
  <div :class="`success-popup ${displayNone && 'display-none'}`">
    <div class="success-popup__container">
      <div class="success-popup__container--heading">
        <span
          >Your pitch deck file size exceeds the limit of 5MB. Please reduce the
          size of the file.</span
        >
      </div>
      <br />
      <p>You can use these online tools to reduce your file size.</p>
      <p>
        > If you are uploading a PDF file:
        <a href="https://www.ilovepdf.com/compress_pdf"
          >Use this online tool.</a
        >
      </p>
      <p>
        > If you are uploading a PPT/PPTX file:
        <a href="https://www.zamzar.com/compress-ppt/">Use this online tool</a>
      </p>
      <a href="#" @click="displayNone = true" class="btn">Close</a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      displayNone: false,
    };
  },
  mounted: function () {
    // this.displayNone = false;
  },
};
</script>

<style lang="scss">
.display-none {
  display: none;
}
.success-popup {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 9999;
  background-color: rgba(0, 0, 0, 0.5);
  &__container {
    position: sticky;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    padding: 20px 40px;
    background-color: rgb(218, 218, 218);
    width: 500px;

    @media screen and (max-width: 600px) {
      width: 350px;
      transform: translate(-7%, -50%);
    }
    &--heading {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 20px;
      margin-bottom: 20px;
      span {
        display: block;
        font-size: 24px;
        font-weight: 700;

        @media screen and (max-width: 600px) {
          font-size: 16px;
        }
      }
      .icon-container {
        height: 30px;

        img {
          height: 100%;
          object-fit: contain;
        }
      }
    }
    p {
      @media screen and (max-width: 600px) {
        font-size: 13px;
      }
    }
    .btn {
      display: block;
      width: max-content;
      padding: 8px 30px;
      color: white;
      background-color: #1e87f0;
      font-size: 16px;
      text-decoration: none;
      border-radius: 5px;
      margin: 50px auto 0 auto;
      transition: all 0.3s;

      @media screen and (max-width: 600px) {
        padding: 6px 25px;
        font-size: 13px;
      }

      &:hover {
        background-color: #1e87f0e7;
      }
    }
  }
}
</style>
