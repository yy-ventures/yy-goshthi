<template>
  <div id="form-area">
    <div id="app">
      <section class="pen-description">
        <h1>Sign up form <br />with multiple steps in VueJS</h1>
      </section>
      <section class="register" v-if="!hasSeenCongrats">
        <div class="register-icon">
          <img
            class="register-icon-item"
            src="https://vuejs.org/images/logo.png"
            alt="vue logo"
          />
        </div>

        <h2 class="register-title">Sign up for a new account</h2>

        <div class="register-stepper">
          <div
            class="step"
            :class="{ 'step-active': step === 1, 'step-done': step > 1 }"
          >
            <span class="step-number">1</span>
          </div>
          <div
            class="step"
            :class="{ 'step-active': step === 2, 'step-done': step > 2 }"
          >
            <span class="step-number">2</span>
          </div>
          <div
            class="step"
            :class="{ 'step-active': step === 3, 'step-done': step > 3 }"
          >
            <span class="step-number">3</span>
          </div>
        </div>

        <transition name="slide-fade">
          <section v-show="step === 1">
            <form class="form" method="post" action="#" @submit.prevent="next">
              <div class="enterprise-info-container">
                <div class="enterprise-name">
                  <h5 class="required no-margin">Name of your enterprise</h5>
                </div>
                <div class="enterprise-name-field">
                  <input
                    type="text"
                    v-model="enterpriseName"
                    id="enterpriseName"
                  />
                  <small>error message</small>
                </div>
                <div class="enterprise-summary">
                  <h5 class="required no-margin">
                    Summary of your enterprise <span>(100 words max)</span>
                  </h5>
                </div>
                <div class="enterprise-summary-field">
                  <textarea
                    v-model="enterpriseSummary"
                    id="enterpriseSummary"
                    cols="30"
                    rows="8"
                    maxlength="500"
                  ></textarea>
                  <small>error message</small>
                </div>
                <div class="enterprise-mission">
                  <h5 class="required no-margin">Mission</h5>
                </div>
                <div class="enterprise-mission-field">
                  <textarea
                    v-model="enterpriseMission"
                    id="enterpriseMission"
                    maxlength="300"
                    cols="50"
                    rows="5"
                  ></textarea>
                  <small>error message</small>
                </div>
                <div class="enterprise-vision">
                  <h5 class="required no-margin">Vision</h5>
                </div>
                <div class="enterprise-vision-field">
                  <textarea
                    v-model="enterpriseVision"
                    id="enterpriseVision"
                    maxlength="300"
                    cols="50"
                    rows="5"
                  ></textarea>
                  <small>error message</small>
                </div>
                <div class="enterprise-social-media">
                  <h5 class="no-margin">Enterprise Social Media Handle</h5>
                </div>
                <div class="enterprise-social-media-field">
                  <input
                    type="text"
                    v-model="enterpriseSocialMedia"
                    id="enterpriseSocialMedia"
                  />
                  <small>error message</small>
                </div>
                <div class="enterprise-website">
                  <h5 class="no-margin">Enterprise Website</h5>
                </div>
                <div class="enterprise-website-field">
                  <input
                    type="text"
                    v-model="enterpriseWebsite"
                    id="enterpriseWebsite"
                  />
                  <small>error message</small>
                </div>
              </div>

              <div
                class="cta"
                data-style="see-through"
                data-alignment="right"
                data-text-color="custom"
              >
                <p class="cta-color">
                  <span class="link_wrap">
                    <input type="submit" value="Next" class="link_text" />
                    <span class="arrow-next"></span>
                  </span>
                </p>
              </div>
            </form>
          </section>
        </transition>
        <transition name="slide-fade">
          <section v-show="step === 2">
            <form class="form" method="post" action="#" @submit.prevent="next">
              <div class="form-group">
                <input
                  type="text"
                  v-model="customer.address"
                  autocomplete="customer.address"
                  placeholder="Address"
                  required
                />
              </div>
              <div class="form-group">
                <input
                  type="text"
                  v-model="customer.zipCode"
                  autocomplete="customer.zipCode"
                  placeholder="Zip Code"
                  minlength="5"
                  maxlength="5"
                  required
                />
                <input
                  type="text"
                  v-model="customer.city"
                  autocomplete="customer.city"
                  placeholder="City"
                  required
                />
              </div>

              <div class="form-group cta-step">
                <div class="cta prev">
                  <p class="cta-color">
                    <span class="link_wrap">
                      <a class="link_text" href="#" @click.prevent="prev()"
                        ><span class="arrow-prev"></span>Previous
                      </a>
                    </span>
                  </p>
                </div>
                <div class="cta">
                  <p class="cta-color">
                    <span class="text"></span>
                    <span class="link_wrap">
                      <input type="submit" value="Next" class="link_text" />
                      <span class="arrow-next"></span>
                    </span>
                  </p>
                </div>
              </div>
            </form>
          </section>
        </transition>
        <transition name="slide-fade">
          <section v-show="step === 3">
            <form class="form" action="#" @submit.prevent="customerRegister">
              <div class="form-group">
                <input
                  type="email"
                  v-model="customer.eMail"
                  autocomplete="customer.eMail"
                  placeholder="Email"
                  required
                />
              </div>
              <div class="form-group">
                <input
                  type="date"
                  v-model="customer.birthDay"
                  placeholder="Birthday ('day'/'month'/'year')"
                  required
                />
              </div>

              <div class="form-group cta-step">
                <div class="cta prev">
                  <p class="cta-color">
                    <span class="link_wrap">
                      <a class="link_text" href="#" @click.prevent="prev()"
                        ><span class="arrow-prev"></span>Previous
                      </a>
                    </span>
                  </p>
                </div>
              </div>
              <div class="register-btn">
                <input type="submit" value="Créer mon compte" />
                <input
                  type="submit"
                  @click="submissionTypeSubmit"
                  id="submitButton"
                />
              </div>
            </form>
          </section>
        </transition>
      </section>
      <section class="congrats register" v-if="hasSeenCongrats">
        <div class="register-icon">
          <img
            class="register-icon-item"
            src="https://vuejs.org/images/logo.png"
            alt="vue logo"
          />
        </div>
        <h2 class="congrats-title">Thank you !</h2>
        <p class="congrats-subtitle">
          You have successfully created your account and joined the<br />
          <strong>VueJS<br />multiple steps form</strong>
        </p>
      </section>
      <section class="pen-description">
        <p style="color: #fff">by</p>
        <a
          href="https://www.behance.net/TMMcreation"
          target="_blank"
          class="pen-copyright"
        >
          <img
            height="70"
            width="70"
            src="https://mir-s3-cdn-cf.behance.net/user/230/3855631.53be57a2b99fb.jpg"
            alt="Digital strategist - Web designer"
          />
        </a>
      </section>
    </div>
  </div>
</template>
<script>
export default {
  //   el: "#app",
  data: () => {
    return {
      enterpriseName: "",
      enterpriseSummary: "",
      enterpriseMission: "",
      enterpriseVision: "",
      enterpriseSocialMedia: "",
      enterpriseWebsite: "",
      team: "",
      cofounderName1: "",
      gender1: "",
      email1: "",
      phone1: "",
      linkedin1: "",
      cofounderName2: "",
      gender2: "",
      email2: "",
      phone2: "",
      linkedin2: "",
      reduceProblem: [],
      howEnterpriseReduce: "",
      impactMeasure: "",
      methodology: "",
      enterpriseInnovation: "",
      enterpriseInnovationMore: "",
      stage: "",
      registered: "",
      legalStatus: "",
      legalStatusOther: "",
      enterpriseMakeMoney: "",
      revenue: "",
      customers: "",
      media_link_1: "",
      media_link_2: "",
      media_link_3: "",
      media_link_4: "",
      media_links: [],
      year: "2022",
      season: "Spring",
      file: "",
      checkFile: "",
      show_message: false,
      show_draft_success_message: false,
      errors: [],
      appId: "",
      password: "",
      steps: {},
      step: 1,
      customer: {
        gender: "1",
        firstName: "",
        lastName: "",
        phoneNumber: "",
        address: "",
        zipCode: "",
        city: "",
        birthDay: "",
        termOfService: "",
        pinCode: "",
        eMail: "",
      },
      hasSeenCongrats: false,
      tempCustomer: {
        gender: "",
        firstName: "",
        lastName: "",
        phoneNumber: "",
        address: "",
        zipCode: "",
        city: "",
        birthDay: "",
        termOfService: "",
        pinCode: "",
        eMail: "",
      },
    };
  },
  methods: {
    prev() {
      this.step--;
    },

    next() {
      this.step++;
    },

    customerRegister: function () {
      this.hasSeenCongrats = true;
    },

    submit: async function (e) {
      const success = this.checkInput(e);
      const data = this.setFormData();
      data.set("is_submission", true);
      localStorage.clear();
      if (success) {
        this.disableSubmitButton();
        this.disableDraftButton();
        axios
          .post(
            "https://yyv.yyventures.org/api/yyg-application-submit-form/create",
            data
          )
          .then((response) => {
            if (response.data.success == true) {
              this.show_message = true;
            }
          })
          .catch((error) => {
            console.log(error);
          });
      }
    },
    submissionTypeSubmit: function (e) {
      //   this.submission = true;
      //   const success = this.checkInput(e);
      const data = this.setFormData();
      //   data.set("is_submission", true);
      localStorage.clear();
      if (success) {
        this.disableSubmitButton();
        this.disableDraftButton();
        axios
          .post(
            "https://yyv.yyventures.org/api/yyg-application-submit-form/create",
            data
          )
          .then((response) => {
            if (response.data.success == true) {
              this.show_message = true;
              data.set("is_submission", true);
            }
          })
          .catch((error) => {
            console.log(error);
          });
      }
    },
    setFormData: function () {
      this.media_links = [];
      if (this.media_link_1) {
        this.media_links.push(this.media_link_1);
      }
      if (this.media_link_2) {
        this.media_links.push(this.media_link_2);
      }

      if (this.media_link_3) {
        this.media_links.push(this.media_link_3);
      }

      if (this.media_link_4) {
        this.media_links.push(this.media_link_4);
      }

      const data = new FormData();
      console.log(this.enterpriseName);
      data.set("name_of_business", this.enterpriseName);
      data.set("summery_of_experience", this.enterpriseSummary);
      data.set("mission", this.enterpriseMission);
      data.set("vision", this.enterpriseVision);
      data.set("enterprise_social_media", this.enterpriseSocialMedia);
      //   data.set("enterprise_website", this.enterpriseWebsite);

      //   data.set("founder_type", this.team);
      //   data.set("co_founder_name_one", this.cofounderName1);
      //   data.set("co_founder_gender_one", this.gender1);
      //   data.set("co_founder_email_one", this.email1);
      //   data.set("co_founder_mobile_one", this.phone1);
      //   data.set("co_founder_linkedin_one", this.linkedin1);
      //   data.set("co_founder_name_two", this.cofounderName2);
      //   data.set("co_founder_gender_two", this.gender2);
      //   data.set("co_founder_email_two", this.email2);
      //   data.set("co_founder_mobile_two", this.phone2);
      //   data.set("co_founder_linkedin_two", this.linkedin2);

      //   data.set("reduce_problem", this.reduceProblem.toString());
      //   data.set("reduce_problem_process", this.howEnterpriseReduce);
      //   data.set("is_known_impact_of_work", this.impactMeasure);
      //   data.set("methodology_of_work", this.methodology);
      //   data.set("innovation", this.enterpriseInnovation);
      //   data.set("experience_of_innovation", this.enterpriseInnovationMore);
      //   data.set("stage_of_ventures", this.stage);
      //   data.set("is_registered_under_law", this.registered);
      //   data.set("legal_status_ventures", this.legalStatusOption());
      //   data.set("make_money_plan", this.enterpriseMakeMoney);
      //   data.set("current_revenue_range", this.revenue);
      //   data.set("customer_range", this.customers);
      //   data.set("media_links", this.media_links);
      //   data.set("year", this.year);
      //   data.set("season", this.season);
      //   data.set("pitch_deck", this.file);

      return data;
    },
  },
  //   data: () => {
  //     return {
  //       formPosition: 0,
  //       animation: "animate-in",
  //       formGroup: [
  //         {
  //           title: "Personal Details",
  //           fields: [
  //             { label: "First Name", value: "" },
  //             { label: "Second Name", value: "" },
  //             { label: "Age", value: "" },
  //           ],
  //         },
  //         {
  //           title: "Address",
  //           fields: [
  //             { label: "City", value: "" },
  //             { label: "Zip Code", value: "" },
  //             { label: "County", value: "" },
  //             { label: "State", value: "" },
  //           ],
  //         },
  //         {
  //           title: "Academic Details",
  //           fields: [
  //             { label: "Academic qualification", value: "" },
  //             { label: "College Attended", value: "" },
  //             { label: "Year of completion", value: "" },
  //           ],
  //         },
  //       ],
  //     };
  //   },
  //   methods: {
  //     nextStep() {
  //       this.animation = "animate-out";
  //       setTimeout(() => {
  //         this.animation = "animate-in";
  //         this.formPosition += 1;
  //       }, 600);
  //     },
  //   },
};
</script>
<style lang="scss" scoped>
#form-area {
  padding: 10rem 20rem;
  height: 300vh;

  //   article {
  //     header {
  //       background-color: plum;

  //       display: flex;
  //       align-content: center;
  //       justify-content: center;

  //       div {
  //         height: 3rem;
  //         width: 3rem;
  //       }
  //     }
  //   }
  // }
  // .active {
  //   background-color: aqua;
  // }
  // .animation-in {
  //   transform-origin: left;
  //   animation: in 0.6s ease-in-out;
  // }
  // .animation-out {
  //   transform-origin: bottom left;
  //   animation: out 0.6s ease-in-out;
  /* VARIABLES */
  /* COLORS */
  $brand-primary: #00c4b5;
  $brand-secondary: #dedc00;
  $brand-lemon: #fff219;
  $brand-quaternary: #f282a5;
  $brand-menthol: #14877d;
  $brand-coral: rgb(250, 90, 85);
  $brand-paprika: rgb(205, 0, 125);
  $color-white: #fff;
  $color-dark: #676767;
  $color-gray: #cecece;
  $color-lightgray: #ededed;
  $color-jungle: #193805;

  /* FONT */
  $font-montserrat: "Montserrat", sans-serif;
  $font-weight-bold: 700;

  body {
    background-color: $color-jungle;
    font-family: $font-montserrat;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  .pen-description {
    display: flex;
    flex-flow: column;
    align-items: center;
    font-family: $font-montserrat;

    h1 {
      text-align: center;
      margin-top: 2rem;
      color: $color-white;
    }

    p {
      margin: 0;
      line-height: 1;
    }

    .pen-copyright {
      img {
        border-radius: 25px;
        padding: 5px;
        margin: 5px;
        transition: box-shadow 0.5s ease-in-out;
      }

      &:hover img {
        box-shadow: 0 10px 20px #0e2101;
      }
    }
  }

  .register {
    display: block;
    color: $color-white;
    max-width: 540px;
    margin: 2rem auto;
    padding: 2rem;
    border-radius: 4rem;
    background: $color-jungle;
    background: linear-gradient(145deg, #173205, #1b3c05);
    box-shadow: 38px 38px 77px #132a04, -38px -38px 77px #1f4606;

    &-icon {
      display: flex;
      background: $color-white;
      border-radius: 2rem;
      width: 50px;
      height: 50px;
      padding: 1rem;
      margin: -50px auto 20px;
      box-shadow: 20px 20px 60px #153004, -20px -20px 60px #1d4006;

      &-item {
        width: 100%;
      }
    }

    &-title {
      font-weight: 300;
      font-size: 1.5rem;
      text-transform: uppercase;
      letter-spacing: 0.2rem;
      text-align: center;
      color: $color-white;
      padding: 0 2rem;
      margin-top: 2rem;
    }

    &-stepper {
      display: flex;
      justify-content: space-between;
      width: 100%;
      position: relative;
      margin: 0 auto 1.5em;

      &::before {
        z-index: 0;
        content: "";
        display: block;
        position: absolute;
        height: 2px;
        top: calc(50% - 1px);
        background: $color-gray;
        width: calc(100% - 20px);
      }

      .step {
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 2;
        border: 2px solid $color-gray;
        color: $color-gray;
        background-color: $color-white;
        border-radius: 50%;
        min-width: 25px;
        min-height: 25px;
        line-height: 20px;
        font-size: 16px;

        &-active {
          color: $brand-primary;
          background-color: $color-white;
          border-color: $brand-primary;
        }

        &-done {
          color: #a7e4b5;
          border-color: #a7e4b5;
        }

        &-number {
          font-family: $font-montserrat;
          font-weight: 800;
          line-height: 1;
          vertical-align: middle;
        }
      }
    }

    .form {
      &-group {
        display: flex;
        flex-flow: row;
        justify-content: flex-start;
        align-items: baseline;

        label {
          text-align: left;
          font-size: 1.1rem;
          line-height: 1.1;
          padding-bottom: 0.5rem;
        }

        &.cta-step {
          color: $color-white;
          justify-content: space-between;

          .cta.prev {
            padding: 10px 30px;
          }
        }

        &.new-password {
          margin-top: 2rem;
        }
      }

      .cta-color,
      .cta-color input,
      .cta-color .link_text {
        color: $color-white;
        font-family: $font-montserrat;
        font-size: 1.1rem;
        text-decoration: none;
      }

      .cta-color .link_wrap {
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;

        .arrow-prev {
          position: relative;
          display: inline-block;
          transform: translate(0);
          transition: transform 0.3s ease-in-out;

          &::before {
            content: "<";
            position: absolute;
            top: -17px;
            left: -25px;
          }
        }

        .arrow-next {
          position: relative;
          display: inline-block;
          transform: translate(0);
          transition: transform 0.3s ease-in-out;

          &::before {
            content: ">";
            position: absolute;
            top: -10px;
            left: -25px;
          }
        }

        &:hover .arrow-prev {
          transform: translate(-5px);
        }

        &:hover .arrow-next {
          transform: translate(5px);
        }
      }
    }
    // Override styles for input
    input[type="submit"],
    input[type="text"],
    input[type="tel"],
    input[type="email"],
    input[type="date"] {
      -webkit-appearance: none;
      border: 0;
      border-radius: 5px;
      padding: 1.3rem 1rem;
      width: 100%;
      margin: 0.5rem;
    }

    input[type="submit"] {
      cursor: pointer;
      position: relative;
      padding-right: 36px;
      background: none;
      width: fit-content;

      &:hover,
      &:focus {
        box-shadow: unset;
        transform: none;
      }

      &::after {
        content: "";
        display: block;
        position: absolute;
        right: 0;
        top: 50%;
        border-radius: 50px;
        border: 1px solid $brand-primary;
        height: 25px;
        width: 25px;
        margin-top: -14px;
        pointer-events: none;
        transition: all 0.33s cubic-bezier(0.12, 0.75, 0.4, 1);
      }
    }

    &-btn input {
      color: $color-white;
      font-size: 1.2rem;
      font-family: $font-montserrat;
      font-weight: 800;
      line-height: 1;
      width: fit-content;
      background: linear-gradient(145deg, #1b3c05, #173205);
      box-shadow: 20px 20px 60px #142c04, -20px -20px 60px #1f4406;

      &:hover {
        background: linear-gradient(145deg, #173205, #1b3c05);
        box-shadow: 20px 20px 60px #142c04, -20px -20px 60px #1f4406;
      }
    }

    // Transition SLIDE FADE
    .slide-fade-enter-active {
      transition: all 0.3s ease;
    }
    .slide-fade-leave-active {
      display: none;
      transition: all 0.4s cubic-bezier(1, 0.5, 0.8, 1);
    }
    .slide-fade-enter,
    .slide-fade-leave-to {
      transform: translateX(10px);
      opacity: 0;
    }
  }

  .congrats {
    background: $color-white;
    color: $brand-primary;
    padding: 4rem;
    text-align: center;

    &-subtitle {
      line-height: 1.3;

      strong {
        font-size: 2rem;
      }
    }
  }
}
</style>
