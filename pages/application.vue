import { form } from "~/assets/scripts/api";
<template>
  <div id="application">
    <div class="heading-container">
      <div class="img-container">
        <img
          src="../assets/images/landing-new-image/yyg-logo/yyg-logo-color.png"
          alt="YY Goshthi logo"
        />
      </div>
      <div class="heading">
        <span>Fall Cohort 2022</span>
      </div>
    </div>
    <!-- <h1 class="heading"> YY Goshthi Spring {{getCurrentyear()}}</h1> -->
    <!-- <no-ssr> -->
    <form id="form" @submit="submit">
      <div class="form-heading-container">
        <h1 class="form-heading-container__heading">Application Form</h1>
      </div>
      <!-- start application start -->
      <div class="info-container" v-if="step === 0">
        <h3>Program Information</h3>
        <p>
          YY Goshthi Incubation Program is created for early-stage Social
          Businesses that helps socially and environmentally conscious
          entrepreneurs to launch their minimum viable product and raise the
          needed seed capital.
        </p>
        <p>
          As the prime Social Business incubation program in Bangladesh, YY
          Goshthi’s goal is to support young social entrepreneurs while they
          build Social Businesses to transform their communities.
        </p>
        <p>
          The incubation program offers four (4) months of rapid, intense, and
          immersive education through world class mentorship, tailored
          consultation, access to investor network, pro-bono business support
          services, office space, and access to a thriving community of YY
          Goshthi alumni.
        </p>
        <p>
          The application process is highly competitive, and only the best
          applicants will proceed to the next stage of our multi-step selection
          process. Please take your time to fill this application, and reach out
          to us if you need any support.
        </p>
        <h3>Who are we looking for:</h3>
        <p>
          We are looking for social enterprises that are operating in Bangladesh
          and working to solve a pressing issue that affects our people and our
          planet. They should strive to make lives and communities better, and
          have a proven track record and business model that works.
        </p>
        <p>
          We encourage enterprises working towards the United Nations’
          Sustainable Development Goals (SDGs) to apply for this incubation
          program, and create a world of three zeros - Zero Poverty, Zero
          Unemployment and Zero Net Carbon Emission.
        </p>
        <div class="steps-btn-container">
          <button @click="next" type="button">Start Your Application</button>
        </div>
      </div>
      <!-- start application end -->

      <!-- step bar start -->
      <header class="progressbar" v-if="step >= 1">
        <div class="progress" id="progress"></div>
        <div v-for="(position, index) in formPosition" :key="index">
          <span :class="{ active: position <= step }">{{ position }}</span>
        </div>
      </header>
      <!-- step bar end -->

      <!-- step 2 start -->
      <div v-if="step === 1">
        <div class="step">
          <p class="step__title">Section 01: FOUNDERS</p>
        </div>

        <!-- question 1 start -->
        <div class="enterprise-name">
          <h5 class="required no-margin">
            What is the name of your enterprise?
          </h5>
        </div>
        <div class="enterprise-name-field">
          <input type="text" v-model="enterpriseName" id="enterpriseName" />
          <small></small>
        </div>
        <!-- question 1 end -->
        <!-- question 7 start -->
        <h5 class="required">How many founders are on the team?</h5>
        <div class="box" id="team">
          <select
            class="founder-dropdown"
            name="numberOfFounder"
            v-model="numberOfFounder"
            id="numberOfFounder"
          >
            <option value="" selected disabled>Select</option>
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
            <option value="5">5</option>
          </select>
          <small></small>
        </div>
        <!-- question 7 end -->
        <!-- note start -->
        <ol>
          <li>
            We encourage enterprises with at least two (2) co-founders to apply
            for the YY Goshthi Incubation program; among which, at least one (1)
            co-founder must be female.
          </li>
          <li>
            If your enterprise is selected, it is mandatory for both co-founders
            to attend and fully participate in all events organised as a part of
            the incubation program.

            <ul>
              <li>
                If there is only one Founder on your team, please ensure that a
                senior colleague from your core team is committing to fully
                participate in the incubation program along with the Founder.
              </li>
              <li>
                Similarly, if you do not have a female co-founder on the team,
                please invite a senior female colleague from the core team to
                fully participate in the incubation program along with the
                Founder.
              </li>
            </ul>
          </li>
        </ol>
        <!-- note end -->
        <!-- question 8 start -->
        <div class="cofounder-container">
          <!-- Co-founder 1 -->
          <div class="box-1">
            <h5 class="required">Co-founder 1</h5>
            <div class="co-founder">
              <div class="co-founder__name">
                <label for="co-founder_1">Name:</label>
              </div>
              <div class="co-founder__name-field">
                <input type="text" id="co-founder_1" v-model="cofounderName1" />
                <small></small>
              </div>
              <div class="co-founder__gender">
                <label>Gender:</label>
              </div>
              <div class="co-founder__gender-field">
                <div class="gender-container" id="gender1">
                  <div class="box">
                    <div class="option">
                      <input
                        type="radio"
                        id="male1"
                        class="gender1"
                        v-model="gender1"
                        name="gender1"
                        value="Male"
                      />
                      <label for="male1">Male</label>
                    </div>
                    <div class="option">
                      <input
                        type="radio"
                        id="female1"
                        class="gender1"
                        v-model="gender1"
                        name="gender1"
                        value="Female"
                      />
                      <label for="female1">Female</label>
                    </div>
                    <div class="option">
                      <input
                        type="radio"
                        id="not-prefer1"
                        class="gender1"
                        v-model="gender1"
                        name="gender1"
                        value="Prefer not to say"
                      />
                      <label for="not-prefer1">Prefer not to say</label>
                    </div>
                  </div>
                  <small></small>
                </div>
              </div>
              <div class="co-founder__email">
                <label for="email1">Email:</label>
              </div>
              <div class="co-founder__email-field">
                <input type="text" v-model="email1" name="email1" id="email1" />
                <small></small>
              </div>
              <div class="co-founder__phone">
                <label for="tel1">Phone:</label>
              </div>
              <div class="co-founder__phone-field">
                <input type="tel" v-model="phone1" name="tel1" id="tel1" />
                <small></small>
              </div>
              <div class="co-founder__linkedin">
                <label for="linkedin1">LinkedIn:</label>
              </div>
              <div class="co-founder__linkedin-field">
                <input
                  type="text"
                  v-model="linkedin1"
                  name="linkedin1"
                  id="linkedin1"
                />
                <small></small>
              </div>
            </div>
          </div>
          <!-- Co-founder 2 -->
          <div class="box-2">
            <h5 class="required">Co-founder 2</h5>
            <div class="co-founder">
              <div class="co-founder__name">
                <label for="co-founder_2">Name:</label>
              </div>
              <div class="co-founder__name-field">
                <input type="text" id="co-founder_2" v-model="cofounderName2" />
                <small></small>
              </div>
              <div class="co-founder__gender">
                <label>Gender:</label>
              </div>
              <div class="co-founder__gender-field">
                <div class="gender-container" id="gender2">
                  <div class="box">
                    <div class="option">
                      <input
                        type="radio"
                        id="male2"
                        class="gender2"
                        v-model="gender2"
                        name="gender2"
                        value="Male"
                      />
                      <label for="male2">Male</label>
                    </div>
                    <div class="option">
                      <input
                        type="radio"
                        id="female2"
                        class="gender2"
                        v-model="gender2"
                        name="gender2"
                        value="Female"
                      />
                      <label for="female2">Female</label>
                    </div>
                    <div class="option">
                      <input
                        type="radio"
                        id="not-prefer2"
                        class="gender2"
                        v-model="gender2"
                        name="gender2"
                        value="Prefer not to say"
                      />
                      <label for="not-prefer2">Prefer not to say</label>
                    </div>
                  </div>
                  <small></small>
                </div>
              </div>
              <div class="co-founder__email">
                <label for="email2">Email:</label>
              </div>
              <div class="co-founder__email-field">
                <input type="text" v-model="email2" name="email2" id="email2" />
                <small></small>
              </div>
              <div class="co-founder__phone">
                <label for="tel2">Phone:</label>
              </div>
              <div class="co-founder__phone-field">
                <input type="tel" v-model="phone2" name="tel2" id="tel2" />
                <small></small>
              </div>
              <div class="co-founder__linkedin">
                <label for="linkedin2">LinkedIn:</label>
              </div>
              <div class="co-founder__linkedin-field">
                <input
                  type="url"
                  v-model="linkedin2"
                  name="linkedin2"
                  id="linkedin2"
                />
                <small></small>
              </div>
            </div>
          </div>
        </div>
        <!-- question 8 end -->

        <!-- button container -->
        <div class="btn-container">
          <button @click="prev" type="button">Previous</button>
          <div>
            <input
              type="button"
              @click="saveAsDraft"
              id="draftButton"
              value="Save as draft"
            />
            <button @click="next" type="button" id="next-btn">Next</button>
          </div>
        </div>
      </div>
      <!-- step 2 end -->

      <!-- Step 1 start -->
      <div class="enterprise-info-container" v-if="step == 2">
        <div class="step">
          <p class="step__title">Section 02: ENTERPRISE</p>
        </div>

        <!-- question 2 start -->
        <div class="enterprise-summary">
          <h5 class="required no-margin">
            Describe what your enterprise does <span>(100 words max)</span>
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
          <small></small>
        </div>
        <!-- question 2 end -->
        <!-- question 3 start -->
        <div class="about-product">
          <h5 class="required no-margin">
            Describe your product/service <span>(100 words max)</span>
          </h5>
        </div>
        <div class="about-product-field">
          <textarea
            v-model="aboutProduct"
            id="aboutProduct"
            cols="30"
            rows="8"
            maxlength="500"
          ></textarea>
          <small></small>
        </div>
        <!-- question 3 end -->

        <!-- question 4 start -->
        <div class="enterprise-mission">
          <h5 class="required no-margin">
            What is your mission? <span>(60 words max)</span>
          </h5>
        </div>
        <div class="enterprise-mission-field">
          <textarea
            v-model="enterpriseMission"
            id="enterpriseMission"
            maxlength="300"
            cols="50"
            rows="5"
          ></textarea>
          <small></small>
        </div>
        <!-- question 4 end -->
        <!-- question 5 start -->
        <div class="enterprise-vision">
          <h5 class="required no-margin">
            What is your vision? <span>(60 words max)</span>
          </h5>
        </div>
        <div class="enterprise-vision-field">
          <textarea
            v-model="enterpriseVision"
            id="enterpriseVision"
            maxlength="200"
            cols="50"
            rows="5"
          ></textarea>
          <small></small>
        </div>
        <!-- question 5 start -->
        <!-- question 6 start -->
        <div class="enterprise-website">
          <h5 class="no-margin">Enterprise Website (if any)</h5>
        </div>
        <div class="enterprise-website-field">
          <input
            type="text"
            v-model="enterpriseWebsite"
            id="enterpriseWebsite"
          />
          <small></small>
        </div>
        <!-- question 6 end -->
        <!-- button container -->
        <div class="btn-container">
          <button @click="prev" type="button">Previous</button>
          <div>
            <input
              type="button"
              @click="saveAsDraft"
              id="draftButton"
              value="Save as draft"
            />
            <button @click="next" type="button" id="next-btn">Next</button>
          </div>
        </div>
      </div>
      <!-- step 1 end -->

      <!-- step 3 start -->
      <div v-if="step === 3">
        <div class="step">
          <p class="step__title">Section 03: FOCUS AREA</p>
        </div>
        <!-- question 9 start -->
        <h5 class="required">
          Does your enterprise focus on any of the Sustainable Development
          Goals?
        </h5>
        <div class="box-1" id="focusGoal">
          <div
            class="checkbox-option"
            v-for="(sdgData, index) in sdgDatas"
            :key="index"
          >
            <input
              type="checkbox"
              name="sdGoal"
              :id="'order_by' + sdgData.id"
              class="sd-Goal"
              v-model="sdGoal"
              :value="sdgData.id"
            />
            <label :for="'order_by' + sdgData.id">{{ sdgData.title }}</label>
            <small class="sd_goal_error"></small>
          </div>
        </div>
        <!-- question 9 end -->
        <!-- question 10 start -->
        <h5 class="required">
          Does your enterprise work to reduce any of the following:
        </h5>
        <div class="box-1" id="reduceProblems">
          <div class="checkbox-option">
            <input
              type="checkbox"
              name="reduce"
              id="carbon-emission"
              class="reduce"
              v-model="reduceProblem"
              value="Carbon emission"
            />
            <label for="carbon-emission">Carbon emission</label>
          </div>
          <div class="checkbox-option">
            <input
              type="checkbox"
              name="reduce"
              id="unemployment"
              class="reduce"
              v-model="reduceProblem"
              value="Unemployment"
            />
            <label for="unemployment">Unemployment</label>
          </div>
          <div class="checkbox-option">
            <input
              type="checkbox"
              name="reduce"
              id="poverty"
              class="reduce"
              v-model="reduceProblem"
              value="Poverty"
            />
            <label for="poverty">Poverty</label>
          </div>
          <div class="checkbox-option">
            <input
              type="checkbox"
              name="reduce"
              id="none"
              class="reduce"
              v-model="reduceProblem"
              value="None of the above"
            />
            <label for="none">None of the above</label>
          </div>
          <small class="reduceProblems_err"></small>
        </div>
        <!-- question 10 end -->
        <!-- question 11 start -->
        <h5>
          If yes, how is your enterprise reducing carbon emission, creating jobs
          or fighting poverty? <span class="limit">(100 words max)</span>
        </h5>
        <div class="box">
          <textarea
            name="reducing"
            id="howEnterpriseReduce"
            v-model="howEnterpriseReduce"
            maxlength="500"
            cols="30"
            rows="8"
          ></textarea>
          <small class="howEnterpriseReduce_err"></small>
        </div>
        <!-- question 11 end -->

        <!-- button container -->
        <div class="btn-container">
          <button @click="prev" type="button">Previous</button>
          <div>
            <input
              type="button"
              @click="saveAsDraft"
              id="draftButton"
              value="Save as draft"
            />
            <button @click="next" type="button" id="next-btn">Next</button>
          </div>
        </div>
      </div>
      <!-- step 3 end -->

      <!-- step 4 start -->
      <div v-if="step === 4">
        <div class="step">
          <p class="step__title">Section 04: PROGRESS</p>
        </div>
        <!-- question 12 start -->
        <h5 class="required">
          Is your enterprise operating and based in Bangladesh?
        </h5>
        <div class="box" id="enterpriseBase">
          <div class="option">
            <input
              type="radio"
              id="enterpriseInBD_yes"
              class="enterpriseBase"
              v-model="isEnterpriseBaseInBD"
              name="enterpriseBase"
              value="1"
            />
            <label for="enterpriseInBD_yes">Yes</label>
          </div>
          <div class="option">
            <input
              type="radio"
              id="enterpriseInBD_no"
              class="enterpriseBase"
              v-model="isEnterpriseBaseInBD"
              name="enterpriseBase"
              value="0"
            />
            <label for="enterpriseInBD_no">No</label>
          </div>
          <small class="enterpriseBase_err"></small>
        </div>
        <!-- question 12 end -->

        <!-- question 13 start -->
        <h5 class="required">What is the stage of your venture?</h5>
        <div class="box-1" id="ventureStage">
          <div class="box">
            <div class="option">
              <input
                type="radio"
                class="stage-venture"
                id="idea_stage"
                v-model="stage"
                name="stage"
                value="Idea Stage"
              />
              <label for="idea_stage">Idea Stage</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="stage-venture"
                id="pilot_stage"
                v-model="stage"
                name="stage"
                value="Feasibility/Prototype/Pilot Stage"
              />
              <label for="pilot_stage">Feasibility/Prototype/Pilot Stage</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="stage-venture"
                id="growth_stage"
                v-model="stage"
                name="stage"
                value="Growth Stage"
              />
              <label for="growth_stage">Growth Stage</label>
            </div>
          </div>
          <small></small>
        </div>
        <!-- question 13 end -->

        <!-- question 14 start -->
        <h5 class="required">
          Do you have any paid customers as of August 10, 2022?
        </h5>
        <div class="box" id="paidCustomer">
          <div class="option">
            <input
              type="radio"
              id="paidCustomer_yes"
              class="paid-customer"
              v-model="paidCustomer"
              name="paidCustomer"
              value="1"
            />
            <label for="paidCustomer_yes">Yes</label>
          </div>
          <div class="option">
            <input
              type="radio"
              id="paidCustomer_no"
              class="paid-customer"
              v-model="paidCustomer"
              name="paidCustomer"
              value="0"
            />
            <label for="paidCustomer_no">No</label>
          </div>
          <small></small>
        </div>
        <!-- question 14 end -->

        <!-- question 15 start -->
        <div v-if="paidCustomer === '1'">
          <h5 class="required">
            How many customers are you serving right now?
          </h5>
          <div class="box-1" id="customerServed">
            <div class="option">
              <input
                type="radio"
                class="customer-served"
                id="customerServed-a"
                v-model="customerServed"
                name="customerServed"
                value="None"
              />
              <label for="customerServed-a">None</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="customer-served"
                id="customerServed-b"
                v-model="customerServed"
                name="customerServed"
                value="1 - 100"
              />
              <label for="customerServed-b">1 - 100</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="customer-served"
                id="customerServed-c"
                v-model="customerServed"
                name="customerServed"
                value="100 - 1000"
              />
              <label for="customerServed-c">100 - 1000</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="customer-served"
                id="customerServed-d"
                v-model="customerServed"
                name="customerServed"
                value="1000 - 10000"
              />
              <label for="customerServed-d">1000 - 10000</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="customer-served"
                id="customerServed-e"
                v-model="customerServed"
                name="customerServed"
                value="> 10000"
              />
              <label for="customerServed-e">> 10000</label>
            </div>
            <small></small>
          </div>
        </div>
        <!-- question 15 end -->

        <!-- question 16 start -->
        <h5 class="required">
          Have you generated any revenue as of August 10, 2022?
        </h5>
        <div class="box" id="generatedRevenue">
          <div class="option">
            <input
              type="radio"
              id="generatedRevenue_yes"
              class="generated-revenue"
              v-model="generatedRevenue"
              name="generatedRevenue"
              value="1"
            />
            <label for="generatedRevenue_yes">Yes</label>
          </div>
          <div class="option">
            <input
              type="radio"
              id="generatedRevenue_no"
              class="generated-revenue"
              v-model="generatedRevenue"
              name="generatedRevenue"
              value="0"
            />
            <label for="generatedRevenue_no">No</label>
          </div>
          <small></small>
        </div>
        <!-- question 16 end -->

        <!-- question 17 start -->
        <div v-if="generatedRevenue === '1'">
          <h5 class="required">
            How much revenue do you have at the moment (in BDT)?
          </h5>
          <div class="box-1" id="revenueGenerate">
            <div class="option">
              <input
                type="radio"
                class="revenueAmount"
                id="revenue-a"
                v-model="revenue"
                name="revenue"
                value="0 - 100000"
              />
              <label for="revenue-a">0 - 100000</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="revenueAmount"
                id="revenue-b"
                v-model="revenue"
                name="revenue"
                value="100000 - 500000"
              />
              <label for="revenue-b">100000 - 500000</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="revenueAmount"
                id="revenue-c"
                v-model="revenue"
                name="revenue"
                value="500000 - 2000000"
              />
              <label for="revenue-c">500000 - 2000000</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="revenueAmount"
                id="revenue-d"
                v-model="revenue"
                name="revenue"
                value="2000000 - 5000000"
              />
              <label for="revenue-d">2000000 - 5000000</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="revenueAmount"
                id="revenue-e"
                v-model="revenue"
                name="revenue"
                value="> 5000000"
              />
              <label for="revenue-e">> 5000000</label>
            </div>
            <small></small>
          </div>
        </div>
        <!-- question 17 end -->

        <!-- question 18 start -->
        <h5 class="required">
          Please explain how does/will your enterprise make money?
          <span class="limit">(100 words max)</span>
        </h5>
        <div class="box-1">
          <textarea
            id="enterpriseMakeMoney"
            v-model="enterpriseMakeMoney"
            maxlength="500"
            cols="30"
            rows="8"
          ></textarea>
          <small></small>
        </div>
        <!-- question 18 end -->

        <!-- question 19 start -->
        <h5 class="required">
          Do you know how to measure the impact of your work?
        </h5>
        <div class="box" id="measure">
          <div class="option">
            <input
              type="radio"
              id="measure_yes"
              class="measure"
              v-model="impactMeasure"
              name="measure"
              value="1"
            />
            <label for="measure_yes">Yes</label>
          </div>
          <div class="option">
            <input
              type="radio"
              id="measure_no"
              class="measure"
              v-model="impactMeasure"
              name="measure"
              value="0"
            />
            <label for="measure_no">No</label>
          </div>
          <small></small>
        </div>
        <!-- question 19 end -->

        <!-- question 20 start -->
        <h5>
          If yes, please tell us what methodology you use.
          <span class="limit">(100 words max)</span>
        </h5>
        <textarea
          v-model="methodology"
          maxlength="500"
          cols="30"
          rows="8"
        ></textarea>
        <!-- question 20 end -->

        <!-- question 21 start -->
        <h5 class="required">
          Please explain what innovation is your enterprise bringing to the
          local market? <span class="limit">(100 words max)</span>
        </h5>
        <div class="innovation-field">
          <textarea
            id="enterpriseInnovationMore"
            v-model="enterpriseInnovationMore"
            maxlength="500"
            cols="30"
            rows="8"
          ></textarea>
          <small></small>
        </div>
        <!-- question 21 end -->

        <!-- question 22 start -->
        <h5 class="required">
          We respect and welcome both product and process innovation offered by
          enterprises and we would love to know more about your enterprise’s
          innovation:
          <span class="limit">(100 words max)</span>
        </h5>
        <div class="innovation-field">
          <textarea
            id="enterpriseInnovation"
            v-model="enterpriseInnovation"
            maxlength="500"
            cols="30"
            rows="8"
          ></textarea>
          <small></small>
        </div>
        <!-- question 22 end -->

        <!-- question 23 start -->
        <h5 class="required">
          If you have applied to our Previous cohort with the same enterprise,
          did anything change since then? If you are applying with a different
          enterprise, why did you pivot and what was the learning from the last
          idea?
          <span class="limit">(100 words max)</span>
        </h5>
        <div class="newOrOldIdea" id="newOrOldIdea">
          <textarea
            v-model="newOrOldIdea"
            maxlength="500"
            cols="30"
            rows="8"
          ></textarea>
          <small></small>
        </div>
        <!-- question 23 end -->

        <!-- button container -->
        <div class="btn-container">
          <button @click="prev" type="button">Previous</button>
          <div>
            <input
              type="button"
              @click="saveAsDraft"
              id="draftButton"
              value="Save as draft"
            />
            <button @click="next" type="button" id="next-btn">Next</button>
          </div>
        </div>
      </div>
      <!-- step 4 end -->

      <!-- step 5 start -->
      <div v-if="step === 5">
        <div class="step">
          <p class="step__title">Section 05: IDEA</p>
        </div>
        <!-- question 24 start -->
        <h5 class="required">
          What got you into working on this particular idea and what domain of
          expertise do you have in this area?
          <span class="limit">(100 words max)</span>
        </h5>
        <div class="source-of-idea">
          <textarea
            id="sourceOfIdea"
            v-model="sourceOfIdea"
            maxlength="500"
            cols="30"
            rows="8"
          ></textarea>
          <small></small>
        </div>
        <!-- question 24 end -->

        <!-- question 25 start -->
        <h5 class="required">
          How did you come to understand that your product/service has a need in
          the market?
          <span class="limit">(100 words max)</span>
        </h5>
        <div class="understand-need">
          <textarea
            id="understandNeed"
            v-model="understandNeed"
            maxlength="500"
            cols="30"
            rows="8"
          ></textarea>
          <small></small>
        </div>
        <!-- question 25 end -->

        <!-- button container -->
        <div class="btn-container">
          <button @click="prev" type="button">Previous</button>
          <div>
            <input
              type="button"
              @click="saveAsDraft"
              id="draftButton"
              value="Save as draft"
            />
            <button @click="next" type="button" id="next-btn">Next</button>
          </div>
        </div>
      </div>
      <!-- step 5 end -->

      <!-- step 6 start -->
      <div v-if="step === 6">
        <div class="step">
          <p class="step__title">Section 06: LEGAL</p>
        </div>
        <!-- question 26 start -->
        <h5 class="required">
          Is the enterprise registered as an entity under the law of Bangladesh?
        </h5>
        <div class="box-1" id="registered">
          <div class="box">
            <div class="option">
              <input
                type="radio"
                class="registered"
                id="registered_yes"
                v-model="registered"
                name="registered"
                value="1"
              />
              <label for="registered_yes">Yes</label>
            </div>
            <div class="option">
              <input
                type="radio"
                class="registered"
                id="registered_no"
                v-model="registered"
                name="registered"
                value="0"
              />
              <label for="registered_no">No</label>
            </div>
          </div>
          <small></small>
        </div>
        <!-- question 26 end -->

        <!-- question 27 start -->
        <h5 class="mt">If yes, what is the legal status of your venture?</h5>
        <div class="box-1">
          <div class="box">
            <div class="option">
              <input
                type="radio"
                id="limited-company"
                v-model="legalStatus"
                name="legalStatus"
                value="For profit/Limited company"
              />
              <label for="limited-company">For profit/Limited company</label>
            </div>
            <div class="option">
              <input
                type="radio"
                id="ngo-company"
                v-model="legalStatus"
                name="legalStatus"
                value="Non profit/NGO/Foundation"
              />
              <label for="ngo-company">Non profit/NGO/Foundation</label>
            </div>
            <div class="option">
              <input
                type="radio"
                id="sole-proprietorship"
                v-model="legalStatus"
                name="legalStatus"
                value="Sole proprietorship"
              />
              <label for="sole-proprietorship">Sole proprietorship</label>
            </div>
          </div>
          <div class="option h-align">
            <label for="other">Other: </label>
            <input type="text" id="other" v-model="legalStatusOther" />
          </div>
          <small></small>
        </div>
        <!-- question 27 end -->

        <!-- question 28 start -->
        <h5>
          Have you received any funding for your enterprise as of August 10,
          2022? If so, please let us know how much funding you have received,
          from whom you have received (if possible), what it covers and when did
          you receive it.
          <span class="limit">(200 words max)</span>
        </h5>
        <div class="received-funding">
          <textarea
            id="receivedFunding"
            v-model="receivedFunding"
            maxlength="1000"
            cols="60"
            rows="16"
          ></textarea>
          <small></small>
        </div>
        <!-- question 28 end -->

        <!-- question 29 start -->
        <h5>
          Is there anything else we should know about your enterprise?
          <span class="limit">(100 words max)</span>
        </h5>
        <div class="more-about-enterprise">
          <textarea
            id="moreAboutEnterprise"
            v-model="moreAboutEnterprise"
            maxlength="500"
            cols="30"
            rows="8"
          ></textarea>
          <small></small>
        </div>
        <!-- question 29 end -->

        <!-- button container -->
        <div class="btn-container">
          <button @click="prev" type="button">Previous</button>
          <div>
            <input
              type="button"
              @click="saveAsDraft"
              id="draftButton"
              value="Save as draft"
            />
            <button @click="next" type="button" id="next-btn">Next</button>
          </div>
        </div>
      </div>
      <!-- step 6 end -->

      <!-- strep 7 start -->
      <div v-if="step === 7">
        <div class="step">
          <p class="step__title">Section 07: MEDIA AND EXPOSURE</p>
        </div>
        <!-- question 30 start -->
        <h5>
          Please share any media link where your enterprise has been featured
        </h5>
        <div class="media-link-group">
          <input
            type="url"
            v-model="media_link_1"
            id="media_link_1"
            name="media-link"
            placeholder="link 1"
            class="mb"
          />
          <input
            type="url"
            v-model="media_link_2"
            id="media_link_2"
            name="media-link"
            placeholder="link 2"
            class="mb"
          />
          <input
            type="url"
            v-model="media_link_3"
            id="media_link_3"
            name="media-link"
            placeholder="link 3"
            class="mb"
          />
          <input
            type="url"
            v-model="media_link_4"
            id="media_link_4"
            name="media-link"
            placeholder="link 4"
            class="mb"
          />
          <small></small>
        </div>
        <!-- question 30 end -->

        <!-- button container -->
        <div class="btn-container">
          <button @click="prev" type="button">Previous</button>
          <div>
            <input
              type="button"
              @click="saveAsDraft"
              id="draftButton"
              value="Save as draft"
            />
            <button @click="next" type="button" id="next-btn">Next</button>
          </div>
        </div>
      </div>
      <!-- step 7 end -->

      <!-- step 8 start -->
      <div v-if="step === 8">
        <div class="step">
          <p class="step__title">Section 08: Other</p>
        </div>
        <!-- question 31 start -->
        <h5 class="mt">
          How did you hear about the YY Goshthi Incubation Program?
        </h5>
        <div class="box-1">
          <div class="box-8">
            <div class="option">
              <input
                type="radio"
                id="wordOfMouth"
                v-model="sourceOfYY"
                name="sourceOfYY"
                value="Friends & Family"
              />
              <label for="wordOfMouth">Friends & Family</label>
            </div>
            <div class="option">
              <input
                type="radio"
                id="yyGoshthiAlumni"
                v-model="sourceOfYY"
                name="sourceOfYY"
                value="YY Goshthi Alumni"
              />
              <label for="yyGoshthiAlumni">YY Goshthi Alumni</label>
            </div>
            <div class="option">
              <input
                type="radio"
                id="facebook"
                v-model="sourceOfYY"
                name="sourceOfYY"
                value="Facebook"
              />
              <label for="facebook">Facebook</label>
            </div>
            <div class="option">
              <input
                type="radio"
                id="instagram"
                v-model="sourceOfYY"
                name="sourceOfYY"
                value="Instagram"
              />
              <label for="instagram">Instagram</label>
            </div>
            <div class="option">
              <input
                type="radio"
                id="linkedin"
                v-model="sourceOfYY"
                name="sourceOfYY"
                value="Linkedin"
              />
              <label for="linkedin">Linkedin</label>
            </div>
            <div class="option">
              <input
                type="radio"
                id="twitter"
                v-model="sourceOfYY"
                name="sourceOfYY"
                value="Twitter"
              />
              <label for="twitter">Twitter</label>
            </div>
            <div class="option">
              <input
                type="radio"
                id="yyGoshthiWebsite"
                v-model="sourceOfYY"
                name="sourceOfYY"
                value="YY Goshthi Website"
              />
              <label for="yyGoshthiWebsite">YY Goshthi Website</label>
            </div>
            <div class="option">
              <input
                type="radio"
                id="yyVenturesWebsite"
                v-model="sourceOfYY"
                name="sourceOfYY"
                value="YY Ventures Website"
              />
              <label for="yyVenturesWebsite">YY Ventures Website</label>
            </div>
            <div class="option">
              <input
                type="radio"
                id="impactHubNetwork"
                v-model="sourceOfYY"
                name="sourceOfYY"
                value="Impact Hub Network"
              />
              <label for="impactHubNetwork">Impact Hub Network</label>
            </div>
          </div>
          <div class="option h-align">
            <label for="other">Other: </label>
            <input type="text" id="other" v-model="sourceOfYYOther" />
          </div>
          <small></small>
        </div>
        <!-- question 31 end -->

        <!-- button container -->
        <div class="btn-container">
          <button @click="prev" type="button">Previous</button>
          <div>
            <input
              type="button"
              @click="saveAsDraft"
              id="draftButton"
              value="Save as draft"
            />
            <button @click="next" type="button" id="next-btn">Next</button>
          </div>
        </div>
      </div>
      <!-- step 8 end -->

      <!-- step 9 start -->
      <div v-if="step === 9">
        <div class="step">
          <p class="step__title">Section 09: Pitch Deck Upload</p>
        </div>

        <div class="sm-box">
          <h5 class="required">Please upload your pitch deck</h5>
          <p class="important-text">
            **Your pitch deck will be provided with your full application to the
            panel of judges. Please make sure your pitch deck has the following
            components:
          </p>
          <div class="component">
            <ul>
              <li>Problem</li>
              <li>Market Opportunity</li>
              <li>Solution</li>
              <li>Product/Service</li>
              <li>Business Model</li>
            </ul>
            <ul>
              <li>Revenue Structure</li>
              <li>Traction</li>
              <li>Roadmap</li>
              <li>Call to Action</li>
              <li>Team</li>
            </ul>
          </div>
          <div class="option mb-2 pb">
            <div class="container">
              <div class="flex-container" id="pitchDeck">
                <input
                  type="file"
                  id="pitchDeck"
                  @change="handleFileUpload"
                  name="pitch_deck"
                />

                <a
                  class="download-btn"
                  href="/YY_Goshthi_Sample_Pitch_Deck.pdf"
                  download
                  >Download Sample Pitch Deck</a
                >
              </div>
              <small class="pitchdeck-error"></small>
            </div>
          </div>
          <div v-if="pdfError"><PdfErrorPopup /></div>
          <div class="application_info">
            <p>
              <strong
                >Thank you for applying to the YY Goshthi Incubation Program!
              </strong>
            </p>
            <p>
              You will receive a confirmation email when your application has
              been submitted successfully.
            </p>
            <p>
              If you do not receive a confirmation email, or if you have any
              queries, please write to incubator@yy.ventures
            </p>
            <p>
              Please note that we only accept one (1) application per
              enterprise.
            </p>
            <p>Please ensure you have completed all required sections.</p>
            <p><strong>DEADLINE - 8 October, 2022 </strong></p>
          </div>
        </div>

        <!-- button container -->
        <div class="btn-container">
          <button @click="prev" type="button">Previous</button>
          <div>
            <input
              type="submit"
              @click="submissionTypeSubmit"
              id="submitButton"
            />
            <input
              type="button"
              @click="saveAsDraft"
              id="draftButton"
              value="Save as draft"
            />
          </div>
        </div>
      </div>
      <!-- step 9 end -->
    </form>
    <!-- </no-ssr> -->
    <div v-if="this.show_message">
      <SuccessPopup />
    </div>
    <div v-if="this.show_draft_success_message">
      <SuccessDraftPopup
        :appId="this.appId"
        :password="this.password"
        :email1="this.email1"
        :email2="this.email2"
      />
    </div>
  </div>
</template>

<script>
// import { post } from '@/assets/scripts/api';
import axios from "axios";
import SuccessPopup from "../components/landing-page-new/components/SuccessPopup.vue";
import SuccessDraftPopup from "../components/landing-page-new/components/SuccessDraftPopup.vue";
import PdfErrorPopup from "../components/landing-page-new/components/PdfErrorPopup.vue";
export default {
  components: {
    SuccessPopup,
    SuccessDraftPopup,
    PdfErrorPopup,
  },
  data() {
    return {
      formPosition: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      step: 0,
      pdfError: false,
      // section 1
      enterpriseName: "",
      aboutProduct: "",
      enterpriseSummary: "",
      enterpriseMission: "",
      enterpriseVision: "",
      enterpriseWebsite: "",
      // section2
      numberOfFounder: "",

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
      // section 3
      sdgDatas: [],
      sdGoal: [],
      reduceProblem: [],
      howEnterpriseReduce: "",
      // section 4
      isEnterpriseBaseInBD: "",
      stage: "",
      paidCustomer: "",
      customerServed: "",
      generatedRevenue: "",
      revenue: "",
      enterpriseMakeMoney: "",
      impactMeasure: "",
      methodology: "",
      enterpriseInnovationMore: "",
      enterpriseInnovation: "",
      newOrOldIdea: "",
      // section 5
      sourceOfIdea: "",
      understandNeed: "",
      // section 6
      registered: "",
      legalStatus: "",
      legalStatusOther: "",
      receivedFunding: "",
      moreAboutEnterprise: "",
      // section 7
      media_link_1: "",
      media_link_2: "",
      media_link_3: "",
      media_link_4: "",
      media_links: [],
      // section 8
      sourceOfYY: "",
      sourceOfYYOther: "",

      customers: "",
      year: "2022",
      season: "Fall",
      file: "",
      checkFile: "",
      show_message: false,
      show_draft_success_message: false,
      errors: [],
      appId: "",
      password: "",
      // co_founder_email_1: this.setEmail1(),
      // co_founder_email_2: this.setEmail2()
    };
  },
  methods: {
    prev() {
      this.step--;
      window.scrollTo({ top: 300 });
    },

    next() {
      let success = false;
      if (this.step > 0) {
        success = this.checkInput();
        success && this.step++;
      }
      this.step === 0 && this.step++;
      // this.step++;
      window.scrollTo({ top: 300 });
      // this.step++;
      // console.log("step", this.step);
      // this.step++;
      if (this.step > 1) {
        this.updateProgressbar();
      }
    },

    updateProgressbar() {
      const progressActive = document.querySelectorAll(".active");
      const progress = document.getElementById("progress");
      console.log(progressActive.length);
      console.log("step: " + this.step);

      console.log("progress active: " + progressActive);
      console.log("progess: " + progress);

      if (this.step === 2) {
        progress.style.width =
          (progressActive.length / this.step / 4) * 100 + "%";

        console.log(`'step '${this.step}':' ` + progress.style.width);
      }
      if (this.step === 3) {
        progress.style.width = "25%";
        console.log(`'step '${this.step}':' ` + progress.style.width);
      }
      if (this.step === 4) {
        progress.style.width = "37.5%";
        console.log(`'step '${this.step}':' ` + progress.style.width);
      }
      if (this.step === 5) {
        progress.style.width = "50%";
        console.log(`'step '${this.step}':' ` + progress.style.width);
      }
      if (this.step === 6) {
        progress.style.width = "62.5%";
        console.log(`'step '${this.step}':' ` + progress.style.width);
      }
      if (this.step === 7) {
        progress.style.width = "75%";
        console.log(`'step '${this.step}':' ` + progress.style.width);
      }
      if (this.step === 8) {
        progress.style.width = "87.5%";
        console.log(`'step '${this.step}':' ` + progress.style.width);
      }
      if (this.step === 9) {
        progress.style.width = "100%";
        console.log(`'step '${this.step}':' ` + progress.style.width);
      }

      console.log("progress width: " + progress.style.width);
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
      // section 1
      data.set("name_of_business", this.enterpriseName);
      data.set("about_product", this.aboutProduct);
      data.set("summery_of_experience", this.enterpriseSummary);
      data.set("mission", this.enterpriseMission);
      data.set("vision", this.enterpriseVision);
      data.set("enterprise_website", this.enterpriseWebsite);
      // section 2
      data.set("number_of_founders", this.numberOfFounder);
      data.set("co_founder_name_one", this.cofounderName1);
      data.set("co_founder_gender_one", this.gender1);
      data.set("co_founder_email_one", this.email1);
      data.set("co_founder_mobile_one", this.phone1);
      data.set("co_founder_linkedin_one", this.linkedin1);
      data.set("co_founder_name_two", this.cofounderName2);
      data.set("co_founder_gender_two", this.gender2);
      data.set("co_founder_email_two", this.email2);
      data.set("co_founder_mobile_two", this.phone2);
      data.set("co_founder_linkedin_two", this.linkedin2);
      // section 3
      data.set("sustainable_development_goals", this.sdGoal.toString());
      data.set("reduce_problem", this.reduceProblem.toString());
      data.set("reduce_problem_process", this.howEnterpriseReduce);
      // section 4
      data.set("is_operating_based_in_bd", this.isEnterpriseBaseInBD);
      data.set("stage_of_ventures", this.stage);
      data.set("do_have_paid_customer", this.paidCustomer);
      data.set("customer_range", this.customerServed);
      data.set("have_generated_revenue_yet", this.generatedRevenue);
      data.set("current_revenue_range", this.revenue);
      data.set("make_money_plan", this.enterpriseMakeMoney);
      data.set("is_known_impact_of_work", this.impactMeasure);
      data.set("methodology_of_work", this.methodology);
      data.set("experience_of_innovation", this.enterpriseInnovationMore);
      data.set("innovation", this.enterpriseInnovation);
      data.set("same_idea_or_new", this.newOrOldIdea);
      // section 5
      data.set("source_of_idea_expertise_detail", this.sourceOfIdea);
      data.set("how_understand_need", this.understandNeed);
      // section 6
      data.set("is_registered_under_law", this.registered);
      data.set("legal_status_ventures", this.legalStatusOption());
      data.set("recieved_any_funding", this.receivedFunding);
      data.set("more_about_enterprise", this.moreAboutEnterprise);
      // section 7
      data.set("media_links", this.media_links);
      // section 8
      data.set("source_of_knowledge", this.sourceOfYYOption());

      data.set("customer_range", this.customers);
      data.set("year", this.year);
      data.set("season", this.season);
      data.set("pitch_deck", this.file);

      return data;
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

    saveAsDraft: async function (e) {
      const isValid = this.checkDraftMinInput(e);
      const app_id = localStorage.getItem("app_id");

      // Form Data
      const data = this.setFormData();
      if (app_id != null || app_id != undefined || app_id != "") {
        data.set("app_id", app_id);
      }
      data.set("is_submission", false);

      if (isValid) {
        this.step === 9 && this.disableSubmitButton();
        this.disableDraftButton();
        const response = await axios.post(
          "https://yyv.yyventures.org/api/yyg-application-submit-form/create",
          data
        );

        this.appId = response.data.responses.app_id;
        this.password = response.data.responses.generated_password;

        try {
          if (response.data.success == true) {
            this.show_draft_success_message = true;
          }
        } catch (err) {
          console.log(err);
        }
      }
    },
    submissionTypeSubmit: function () {
      this.submission = true;
    },
    disableSubmitButton: function () {
      const submitBtn = document.querySelector("#submitButton");
      submitBtn.disabled = true;
      submitBtn.style.opacity = "0.4";
      submitBtn.style.cursor = "wait";
    },
    disableDraftButton: function () {
      const draftBtn = document.querySelector("#draftButton");
      const nextBtn = document.querySelector("#next-btn");
      draftBtn.disabled = true;
      draftBtn.style.opacity = "0.4";
      draftBtn.style.cursor = "wait";

      if (nextBtn) {
        nextBtn.disabled = true;
        nextBtn.style.opacity = "0.4";
        nextBtn.style.cursor = "wait";
      }
      setTimeout(() => {
        draftBtn.disabled = false;
        draftBtn.style.opacity = "1";
        draftBtn.style.cursor = "pointer";
        if (nextBtn) {
          nextBtn.disabled = false;
          nextBtn.style.opacity = "1";
          nextBtn.style.cursor = "pointer";
        }
      }, 10000);
    },

    getCurrentyear: function () {
      const date = new Date();
      const year = date.getFullYear();
      this.year = year;
    },
    handleFileUpload: function (e) {
      this.checkFile = e.target.files[0];
      if (this.checkFile.size > 5242880) {
        this.pdfError = true;

        // alert(
        //   `Please upload your file between 5MB, your file is ${Math.round(
        //     this.checkFile.size / 1048576
        //   )}MB`
        // );
        e.target.value = "";
      } else {
        this.file = this.checkFile;
      }
    },
    checkInput: function (e) {
      e && e.preventDefault();
      // section 1
      const enterpriseName = document.querySelector("#enterpriseName");
      const aboutProduct = document.querySelector("#aboutProduct");
      const enterpriseSummary = document.querySelector("#enterpriseSummary");
      const enterpriseMission = document.querySelector("#enterpriseMission");
      const enterpriseVision = document.querySelector("#enterpriseVision");
      const enterpriseWebsite = document.querySelector("#enterpriseWebsite");
      // section 2
      const numberOfFounder = document.querySelector("#numberOfFounder");
      const cofounderName1 = document.querySelector("#co-founder_1");
      const gender1 = document.querySelector("#gender1");
      const email1 = document.querySelector("#email1");
      const phone1 = document.querySelector("#tel1");
      const linkedin1 = document.querySelector("#linkedin1");
      const cofounderName2 = document.querySelector("#co-founder_2");
      const gender2 = document.querySelector("#gender2");
      const email2 = document.querySelector("#email2");
      const phone2 = document.querySelector("#tel2");
      const linkedin2 = document.querySelector("#linkedin2");
      // section 3
      const sdGoal = document.querySelector(".sd-Goal");
      const reduceProblem = document.querySelector("#reduceProblems");
      const howEnterpriseReduce = document.querySelector(
        "#howEnterpriseReduce"
      );
      // section 4
      const enterpriseBase = document.querySelector("#enterpriseBase");
      const stageVenture = document.querySelector("#ventureStage");
      const paidCustomer = document.querySelector("#paidCustomer");
      const customerServed = document.querySelector("#customerServed");
      const generatedRevenue = document.querySelector("#generatedRevenue");
      const revenueAmount = document.querySelector("#revenueGenerate");
      const enterpriseMakeMoney = document.querySelector(
        "#enterpriseMakeMoney"
      );
      const impactMeasure = document.querySelector("#measure");
      const enterpriseInnovationMore = document.querySelector(
        "#enterpriseInnovationMore"
      );
      const enterpriseInnovation = document.querySelector(
        "#enterpriseInnovation"
      );
      const newOrOldIdea = document.querySelector("#newOrOldIdea");
      // section 5
      const sourceOfIdea = document.querySelector("#sourceOfIdea");
      const understandNeed = document.querySelector("#understandNeed");
      // section 6
      const registered = document.querySelector("#registered");
      const receivedFunding = document.querySelector("#receivedFunding");
      const moreAboutEnterprise = document.querySelector(
        "#moreAboutEnterprise"
      );

      const customerAmount = document.querySelector("#customerAmount");
      const mediaLink1 = document.querySelector("#media_link_1");
      const mediaLink2 = document.querySelector("#media_link_2");
      const mediaLink3 = document.querySelector("#media_link_3");
      const mediaLink4 = document.querySelector("#media_link_4");
      const pitchDeck = document.querySelector("#pitchDeck");

      let error = false;

      if (this.step === 1) {
        if (this.enterpriseName === "") {
          this.setErrorFor(enterpriseName, "Enterprise name cannot be empty");
          error = true;
        } else {
          this.setSuccessFor(enterpriseName);
        }

        if (this.numberOfFounder === "") {
          this.setErrorForFounders("Choose any option");
          error = true;
        } else {
          this.setSuccessFor(numberOfFounder);
        }

        if (this.cofounderName1 === "") {
          this.setErrorFor(
            cofounderName1,
            "Co-founder name cannot be empty for draft"
          );
          error = true;
        } else {
          this.setSuccessFor(cofounderName1);
        }
        if (this.gender1 === "") {
          this.setErrorForGender1("Choose an option");
          error = true;
        } else {
          this.setSuccessFor(gender1);
        }
        if (this.email1 === "") {
          this.setErrorFor(email1, "email cannot be empty for draft");
          error = true;
        } else if (
          !/^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i.test(
            this.email1
          )
        ) {
          this.setErrorFor(email1, "Not a valid email");
        } else {
          this.setSuccessFor(email1);
        }
        if (this.phone1 === "") {
          this.setErrorFor(phone1, "Phone number cannot be empty for draft");
          error = true;
        } else if (!/[0-9]+/.test(this.phone1)) {
          this.setErrorFor(phone1, "invalid number");
          error = true;
        } else {
          this.setSuccessFor(phone1);
        }

        if (this.cofounderName2 === "") {
          this.setErrorFor(
            cofounderName2,
            "Co-founder name cannot be empty for draft"
          );
          error = true;
        } else {
          this.setSuccessFor(cofounderName2);
        }

        if (this.gender2 === "") {
          this.setErrorForGender2("Choose an option");
          error = true;
        } else {
          this.setSuccessFor(gender2);
        }
        if (this.email2 === "") {
          this.setErrorFor(email2, "email cannot be empty for draft");
          error = true;
        } else if (
          !/^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i.test(
            this.email2
          )
        ) {
          this.setErrorFor(email2, "Not a valid email");
          error = true;
        } else {
          this.setSuccessFor(email2);
        }
        if (this.phone2 === "") {
          this.setErrorFor(phone2, "Phone number cannot be empty for draft");
          error = true;
        } else if (!/[0-9]+/.test(this.phone2)) {
          this.setErrorFor(phone2, "invalid number");
          error = true;
        } else {
          this.setSuccessFor(phone2);
        }
      }
      // Step 2
      if (this.step === 2) {
        // ==========
        if (this.aboutProduct === "") {
          this.setErrorFor(aboutProduct, "field cannot be empty for draft");
          error = true;
        } else {
          this.setSuccessFor(aboutProduct);
        }
        if (this.enterpriseSummary === "") {
          this.setErrorFor(
            enterpriseSummary,
            "Enterprise summary cannot be empty for draft"
          );
          error = true;
        } else {
          this.setSuccessFor(enterpriseSummary);
        }
        if (this.enterpriseMission === "") {
          this.setErrorFor(
            enterpriseMission,
            "Enterprise mission cannot be empty for draft"
          );
          error = true;
        } else {
          this.setSuccessFor(enterpriseMission);
        }
        if (this.enterpriseVision === "") {
          this.setErrorFor(
            enterpriseVision,
            "Enterprise vision cannot be empty for draft"
          );
          error = true;
        } else {
          this.setSuccessFor(enterpriseVision);
        }
        if (this.enterpriseWebsite !== "") {
          if (
            !/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(
              this.enterpriseWebsite
            )
          ) {
            this.setErrorFor(enterpriseWebsite, "Should be an URL");
            error = true;
          } else {
            this.setSuccessFor(enterpriseWebsite);
          }
        }
        // =============
      }
      // Step 3
      if (this.step === 3) {
        if (this.sdGoal.length <= 0) {
          this.setErrorSdgoal("Choose any option");
          error = true;
        } else {
          this.setSuccessFor(sdGoal);
        }
        if (this.reduceProblem.length <= 0) {
          this.setErrorReduceProblem("Choose any option");
          error = true;
        } else {
          this.setSuccessFor(reduceProblem);
        }
      }
      // Step 4
      if (this.step === 4) {
        if (this.isEnterpriseBaseInBD === "") {
          this.setErrorForisEnterpriseBaseInBD("Choose any option");
          error = true;
        } else {
          this.setSuccessFor(enterpriseBase);
        }
        if (this.paidCustomer === "") {
          this.setErrorForPaidCustomer("Choose any option");
          error = true;
        }
        if (this.paidCustomer === 1) {
          if (this.customerServed === "") {
            this.setErrorForCustomerServed("Choose any option");
            error = true;
          } else {
            this.setSuccessFor(customerServed);
          }
          error = true;
        } else {
          this.setSuccessFor(paidCustomer);
        }

        if (this.generatedRevenue === "") {
          this.setErrorForGeneratedRevenue("Choose any option");
          error = true;
        } else {
          this.setSuccessFor(generatedRevenue);
        }
        if (this.generatedRevenue === 1) {
          if (this.revenue === "") {
            this.setErrorForRevenue("Choose any option");
            error = true;
          } else {
            this.setSuccessFor(revenueAmount);
          }
        }
        if (this.stage === "") {
          this.setErrorForVentureStage("Choose any option");
          error = true;
        } else {
          this.setSuccessFor(stageVenture);
        }
        if (this.impactMeasure === "") {
          this.setErrorForMeasure("Choose any option");
          error = true;
        } else {
          this.setSuccessFor(impactMeasure);
        }
        if (this.enterpriseMakeMoney === "") {
          this.setErrorFor(enterpriseMakeMoney, "field cannot be empty");
          error = true;
        } else {
          this.setSuccessFor(enterpriseMakeMoney);
        }
        if (this.enterpriseInnovation === "") {
          this.setErrorFor(enterpriseInnovation, "field cannot be empty");
          error = true;
        } else {
          this.setSuccessFor(enterpriseInnovation);
        }

        if (this.enterpriseInnovationMore === "") {
          this.setErrorFor(enterpriseInnovationMore, "field cannot be empty");
          error = true;
        } else {
          this.setSuccessFor(enterpriseInnovationMore);
        }
        if (this.newOrOldIdea === "") {
          this.setErrorFor(newOrOldIdea, "field cannot be empty");
          error = true;
        } else {
          this.setSuccessFor(newOrOldIdea);
        }
      }
      // Step 5
      if (this.step === 5) {
        if (this.sourceOfIdea === "") {
          this.setErrorFor(sourceOfIdea, "field cannot be empty");
          error = true;
        } else {
          this.setSuccessFor(sourceOfIdea);
        }
        if (this.understandNeed === "") {
          this.setErrorFor(understandNeed, "field cannot be empty");
          error = true;
        } else {
          this.setSuccessFor(understandNeed);
        }
      }
      // Step 6
      if (this.step === 6) {
        if (this.registered === "") {
          this.setErrorForRegistered("Choose any option");
          error = true;
        } else {
          this.setSuccessFor(registered);
        }
      }
      // Step 7

      // Step 8
      if (this.step === 8) {
        console.log("step 8");
      }
      // Step 9
      if (this.step === 9) {
        console.log(this.file);
        if (this.file === "") {
          this.setErrorFor(pitchDeck, "Please upload your pitch deck");
          error = true;
        } else {
          // this.setSuccessFor(pitchDeck);
        }
      }

      // if (this.customers === "") {
      //   this.setErrorForCustomers("Choose any option");
      //   error = true;
      // } else {
      //   this.setSuccessFor(customerAmount);
      // }
      // --------- client side validation --------------->

      return !error;
    },
    checkDraftMinInput: function (e) {
      e.preventDefault();
      // section 1
      const enterpriseName = document.querySelector("#enterpriseName");
      const aboutProduct = document.querySelector("#aboutProduct");
      const enterpriseSummary = document.querySelector("#enterpriseSummary");
      const enterpriseMission = document.querySelector("#enterpriseMission");
      const enterpriseVision = document.querySelector("#enterpriseVision");
      const enterpriseWebsite = document.querySelector("#enterpriseWebsite");
      // section 2
      const numberOfFounder = document.querySelector("#numberOfFounder");
      const cofounderName1 = document.querySelector("#co-founder_1");
      const gender1 = document.querySelector("#gender1");
      const email1 = document.querySelector("#email1");
      const phone1 = document.querySelector("#tel1");
      const linkedin1 = document.querySelector("#linkedin1");
      const cofounderName2 = document.querySelector("#co-founder_2");
      const gender2 = document.querySelector("#gender2");
      const email2 = document.querySelector("#email2");
      const phone2 = document.querySelector("#tel2");
      const team = document.querySelector("#team");
      const linkedin2 = document.querySelector("#linkedin2");
      const draftBtn = document.querySelector("#draftButton");

      let error = false;

      // Step 1
      if (this.step === 1) {
        // ========
        if (this.numberOfFounder === "") {
          this.setErrorForFounders("Choose any option");
          error = true;
        } else {
          this.setSuccessFor(numberOfFounder);
        }

        if (this.cofounderName1 === "") {
          this.setErrorFor(
            cofounderName1,
            "Co-founder name cannot be empty for draft"
          );
          error = true;
        } else {
          this.setSuccessFor(cofounderName1);
        }
        if (this.gender1 === "") {
          this.setErrorForGender1("Choose an option");
          error = true;
        } else {
          this.setSuccessFor(gender1);
        }
        if (this.email1 === "") {
          this.setErrorFor(email1, "email cannot be empty for draft");
          error = true;
        } else if (
          !/^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i.test(
            this.email1
          )
        ) {
          this.setErrorFor(email1, "Not a valid email");
        } else {
          this.setSuccessFor(email1);
        }
        if (this.phone1 === "") {
          this.setErrorFor(phone1, "Phone number cannot be empty for draft");
          error = true;
        } else if (!/[0-9]+/.test(this.phone1)) {
          this.setErrorFor(phone1, "invalid number");
          error = true;
        } else {
          this.setSuccessFor(phone1);
        }

        // not required

        // if(this.linkedin1 === ''){
        //     this.setErrorFor(linkedin1, 'link cannot be empty for draft')
        //     error = true
        // }else if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.linkedin1)){
        //     this.setErrorFor(linkedin1, 'Not a valid URL')
        //     error = true
        // }else{
        //     this.setSuccessFor(linkedin1)
        // }

        if (this.cofounderName2 === "") {
          this.setErrorFor(
            cofounderName2,
            "Co-founder name cannot be empty for draft"
          );
          error = true;
        } else {
          this.setSuccessFor(cofounderName2);
        }

        if (this.gender2 === "") {
          this.setErrorForGender2("Choose an option");
          error = true;
        } else {
          this.setSuccessFor(gender2);
        }
        if (this.email2 === "") {
          this.setErrorFor(email2, "email cannot be empty for draft");
          error = true;
        } else if (
          !/^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i.test(
            this.email2
          )
        ) {
          this.setErrorFor(email2, "Not a valid email");
          error = true;
        } else {
          this.setSuccessFor(email2);
        }
        if (this.phone2 === "") {
          this.setErrorFor(phone2, "Phone number cannot be empty for draft");
          error = true;
        } else if (!/[0-9]+/.test(this.phone2)) {
          this.setErrorFor(phone2, "invalid number");
          error = true;
        } else {
          this.setSuccessFor(phone2);
        }
        // ==========

        if (this.enterpriseName === "") {
          this.setErrorFor(
            enterpriseName,
            "Enterprise name cannot be empty for draft"
          );
          error = true;
        } else {
          this.setSuccessFor(enterpriseName);
        }
        // if (this.aboutProduct === "") {
        //   this.setErrorFor(aboutProduct, "field cannot be empty for draft");
        //   error = true;
        // } else {
        //   this.setSuccessFor(aboutProduct);
        // }
        // if (this.enterpriseSummary === "") {
        //   this.setErrorFor(
        //     enterpriseSummary,
        //     "Enterprise summary cannot be empty for draft"
        //   );
        //   error = true;
        // } else {
        //   this.setSuccessFor(enterpriseSummary);
        // }
        // if (this.enterpriseMission === "") {
        //   this.setErrorFor(
        //     enterpriseMission,
        //     "Enterprise mission cannot be empty for draft"
        //   );
        //   error = true;
        // } else {
        //   this.setSuccessFor(enterpriseMission);
        // }
        // if (this.enterpriseVision === "") {
        //   this.setErrorFor(
        //     enterpriseVision,
        //     "Enterprise vision cannot be empty for draft"
        //   );
        //   error = true;
        // } else {
        //   this.setSuccessFor(enterpriseVision);
        // }
        // if (this.enterpriseSocialMedia !== "") {
        //   if (
        //     !/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(
        //       this.enterpriseSocialMedia
        //     )
        //   ) {
        //     this.setErrorFor(enterpriseSocialMedia, "Should be an URL");
        //     error = true;
        //   } else {
        //     this.setSuccessFor(enterpriseSocialMedia);
        //   }
        // }
        // if (this.enterpriseWebsite !== "") {
        //   if (
        //     !/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(
        //       this.enterpriseWebsite
        //     )
        //   ) {
        //     this.setErrorFor(enterpriseWebsite, "Should be an URL");
        //     error = true;
        //   } else {
        //     this.setSuccessFor(enterpriseWebsite);
        //   }
        // }
      }
      // Step 2
      if (this.step === 2) {
      }
      // Step 3
      if (this.step === 3) {
        console.log("step 3");
      }
      // Step 4
      if (this.step === 4) {
        console.log("step 4");
      }
      // Step 5
      if (this.step === 5) {
        console.log("step 5");
      }
      // Step 6
      if (this.step === 6) {
        console.log("step 6");
      }
      // Step 7
      if (this.step === 7) {
        console.log("step 7");
      }
      // Step 8
      if (this.step === 8) {
        console.log("step 8");
      }
      // Step 9
      if (this.step === 9) {
        console.log("step 9");
      }

      return !error;
    },
    legalStatusOption: function () {
      if (this.legalStatus === "") {
        return this.legalStatusOther;
      }
      return this.legalStatus;
    },
    bindLegalStatusData: function (data) {
      if (
        data === "For profit/Limited company" ||
        data === "Non profit/NGO/Foundation" ||
        data === "Sole proprietorship"
      ) {
        this.legalStatus = data;
        return;
      }
      this.legalStatusOther = data;
    },

    sourceOfYYOption: function () {
      if (this.sourceOfYY === "") {
        return this.sourceOfYYOther;
      }
      return this.sourceOfYY;
    },
    bindsourceOfYYData: function (data) {
      if (
        data === "Facebook" ||
        data === "Instagram" ||
        data === "Linkedin" ||
        data === "Twitter" ||
        data === "Word of Mouth" ||
        data === "YY Goshthi Website" ||
        data === "YY Ventures Website" ||
        data === "Impact Hub Network" ||
        data === "YY Goshthi Alumni"
      ) {
        this.sourceOfYY = data;
        return;
      }
      this.sourceOfYYOther = data;
    },
    setErrorForGender1: function (message) {
      const formControl = document.querySelector("#gender1");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForGender2: function (message) {
      const formControl = document.querySelector("#gender2");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForRegistered: function (message) {
      const formControl = document.querySelector("#registered");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForFounders: function (message) {
      const formControl =
        document.querySelector("#numberOfFounder").parentElement;
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForPaidCustomer: function (message) {
      const formControl = document.querySelector("#paidCustomer");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForCustomerServed: function (message) {
      const formControl = document.querySelector("#paidCustomer");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForMeasure: function (message) {
      const formControl = document.querySelector("#measure");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForGeneratedRevenue: function (message) {
      const formControl = document.querySelector("#generatedRevenue");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForIsEnterpriseBaseInBD: function (message) {
      const formControl = document.querySelector("#enterpriseBase");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForVentureStage: function (message) {
      const formControl = document.querySelector("#ventureStage");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForCustomers: function (message) {
      const formControl = document.querySelector("#customerAmount");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForRevenue: function (message) {
      const formControl = document.querySelector("#revenueGenerate");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorFor: function (input, message) {
      const formControl = input.parentElement;
      const small = formControl.querySelector("small");
      formControl.className = "form-control error";
      small.innerText = message;
    },
    setSuccessFor: function (input) {
      const formControl = input.parentElement;
      const small = formControl.querySelector("small");
      formControl.className = "form-control success";
      small.innerText = "";
    },
    setErrorSdgoal: function (message) {
      const formControl = document.querySelector(".sd-Goal").parentElement;
      const small = formControl.querySelector("small");
      formControl.className = "form-control success";
      small.innerText = message;
    },
    setErrorReduceProblem: function (message) {
      const formControl = document.querySelector("#reduceProblems");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorForisEnterpriseBaseInBD: function (message) {
      const formControl = document.querySelector("#enterpriseBase");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorHowEnterpriseReduce: function (message) {
      const formControl = document.querySelector(
        "#howEnterpriseReduce"
      ).parentElement;
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
    setErrorStage: function (message) {
      const formControl = document.querySelector(".stageVenture");
      const small = formControl.querySelector("small");

      formControl.className = "form-control error";
      small.innerText = message;
    },
  },
  mounted: async function () {
    console.log(this.step);
    // const data = localStorage.getItem('draftData');
    let appId = localStorage.getItem("app_id");
    let draftData;
    let sdgDatas = [];

    const sdgData = await axios.get(
      "https://yyv.yyventures.org/api/get-focus-area-data",
      {
        headers: { "Content-Type": "application/json" },
      }
    );
    sdgDatas = sdgData.data.data;
    this.sdgDatas = sdgDatas;
    console.log(this.sdgDatas);
    // console.log(sdgDatas[0]);
    // const draftData = JSON.parse(data);
    if (appId != null) {
      const headers = {
        "Content-Type": "application/json",
        // 'Authorization': response.data.data.token
      };

      const data = await axios.get(
        `https://yyv.yyventures.org/api/get-app-draft-data?app_id=${appId}`,
        {
          headers: headers,
        }
      );
      draftData = data.data.data;
    }

    if (draftData != null || draftData != undefined) {
      // sectiond 1
      this.enterpriseName = draftData.name_of_business;
      this.aboutProduct = draftData.about_product;
      this.enterpriseSummary = draftData.summery_of_experience;
      this.enterpriseMission = draftData.mission;
      this.enterpriseVision = draftData.vision;
      this.enterpriseWebsite = draftData.enterprise_website;
      // section 2
      this.numberOfFounder = draftData.number_of_founders;
      this.cofounderName1 = draftData.co_founder_name_one;
      this.gender1 = draftData.co_founder_gender_one;
      this.email1 = draftData.co_founder_email_one;
      this.phone1 = draftData.co_founder_mobile_one;
      this.linkedin1 = draftData.co_founder_linkedin_one;
      this.cofounderName2 = draftData.co_founder_name_two;
      this.gender2 = draftData.co_founder_gender_two;
      this.email2 = draftData.co_founder_email_two;
      this.phone2 = draftData.co_founder_mobile_two;
      this.linkedin2 = draftData.co_founder_linkedin_two;
      // section 3
      this.sdGoal = draftData.sustainable_development_goals;
      this.reduceProblem = draftData.reduce_problem; // need to set data
      this.howEnterpriseReduce = draftData.reduce_problem_process;
      // section 4
      this.isEnterpriseBaseInBD = draftData.is_operating_based_in_bd;
      this.stage = draftData.stage_of_ventures;
      this.paidCusotmer = draftData.do_have_paid_customer;
      this.customerServed = draftData.customer_range;
      this.generatedRevenue = draftData.have_generated_revenue_yet;
      this.revenue = draftData.current_revenue_range;
      this.enterpriseMakeMoney = draftData.make_money_plan;
      this.impactMeasure = draftData.is_known_impact_of_work;
      this.methodology = draftData.methodology_of_work;
      this.enterpriseInnovationMore = draftData.experience_of_innovation;
      this.enterpriseInnovation = draftData.innovation;
      this.newOrOldIdea = draftData.same_idea_or_new;
      // section 5
      this.sourceOfIdea = draftData.source_of_idea_expertise_detail;
      this.understandNeed = draftData.how_understand_need;
      // section 6
      this.registered = draftData.is_registered_under_law;
      this.bindLegalStatusData(draftData.legal_status_ventures);
      this.receivedFunding = draftData.recieved_any_funding;
      this.moreAboutEnterprise = draftData.more_about_enterprise;
      // section 7
      if (draftData.media_links != null) {
        this.media_link_1 = draftData.media_links[0];
        this.media_link_2 = draftData.media_links[1];
        this.media_link_3 = draftData.media_links[2];
        this.media_link_4 = draftData.media_links[3];
      }

      // section 8
      this.bindsourceOfYYData(draftData.source_of_knowledge);

      this.file = draftData.pitch_deck;
      this.customers = draftData.customer_range;

      // data.set('media_links',[this.media_link_1, this.media_link_2, this.media_link_3, this.media_link_4]);
    }
  },
};
</script>

<style lang="scss" scoped>
#application {
  position: relative;
  padding: 10rem 5rem;
  // #pitchDeck {
  //   width: 50%;
  // }

  @media screen and (max-width: 600px) {
    padding: 8rem 0;
  }

  .heading-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 10px;
    margin-bottom: 80px;
    width: min-content;
    margin-inline: auto;

    @media screen and (max-width: 600px) {
      padding: 0 20px;
    }
    .img-container {
      height: 100px;

      @media screen and (max-width: 600px) {
        height: 70px;
      }
      img {
        height: 100%;
        object-fit: contain;
      }
    }
    .heading {
      span {
        display: block;
        color: #3a3a3a;
        font-size: 36.5px;
        line-height: 1.2;
        white-space: nowrap;
        text-transform: uppercase;
        font-weight: 300;

        border-block: 2px solid #3a3a3a;

        @media screen and (max-width: 600px) {
          font-size: 25px;
          font-weight: 400;
        }
      }
    }
  }

  form {
    // border: 1px solid black;
    padding: 80px 70px;
    background-color: #e0eef2;
    border-radius: 15px;

    position: relative;

    @media screen and (max-width: 600px) {
      padding: 50px 40px;
      border-radius: 0;
    }

    .info-container {
      h3 {
        color: #000;
        font-weight: 600;
      }
      p {
        color: black;
      }
    }

    .progressbar {
      // background-color: #049abf;
      width: 100%;
      margin-bottom: 5rem;

      position: relative;
      z-index: 1;

      display: flex;
      justify-content: space-between;

      &::after {
        content: "";
        height: 4px;
        width: 100%;
        background-color: #777;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
      }
      .progress {
        position: absolute;
        top: 50%;
        left: 0;
        transform: translate(0, -50%);
        z-index: 1;
        background-color: #049abf;
        width: 0%;
        height: 4px;
      }

      div {
        span {
          background-color: #777;
          color: white;
          display: block;
          height: 2rem;
          width: 2rem;

          position: relative;
          z-index: 11;

          display: flex;
          justify-content: center;
          align-items: center;
          border-radius: 50%;

          @media screen and (max-width: 600px) {
            font-size: 14px;
            height: 1.5rem;
            width: 1.5rem;
          }
        }
        .active {
          background-color: #049abf;
        }
      }
    }

    .form-heading-container {
      background-color: #efd214;
      border-radius: 50px;
      padding: 5px 30px;
      width: min-content;

      position: absolute;
      left: 50%;
      top: -20px;
      transform: translate(-50%);
      &__heading {
        white-space: nowrap;
        margin: 0;
        font-size: 30px !important;
      }
    }
    .founder-dropdown {
      padding: 5px 10px;
      width: 250px;
      border: none;
      font-size: 16px;
      option {
        padding: 5px 10px;
      }
    }
    .steps-btn-container {
      width: 100%;
      margin-top: 5rem;

      display: flex;
      justify-content: center;

      button {
        font-size: 1.2rem;
        padding: 1rem 3rem;
        color: white;
        width: 30%;
        background-color: #049abf;
        border: none;
        cursor: pointer;
        transition: 0.2s all;

        @media screen and (max-width: 600px) {
          width: 100%;
        }

        &:hover {
          background-color: #03738f;
        }
      }
    }
    small {
      display: block;
      white-space: nowrap;
      min-height: 1rem;
    }
    .form-control.success input {
      border-color: #2ecc71;
    }
    .form-control.error input {
      border-color: #e74c3c;
    }
    .form-control.success textarea {
      border-color: #2ecc71;
    }
    .form-control.error textarea {
      border-color: #e74c3c;
    }
    .enterprise-info-container small {
      color: #e74c3c;
      visibility: hidden;
    }
    .box small,
    .co-founder__name-field small,
    .option small,
    .co-founder__email-field small,
    .co-founder__phone-field small,
    .co-founder__linkedin-field small,
    .checkbox-option small,
    .innovation-field small,
    .box-1 small,
    .media-link-group small,
    .gender-container small {
      color: #e74c3c;
      visibility: hidden;
    }
    .form-control.error small {
      color: #e74c3c;
      visibility: visible;
    }

    .step {
      background-color: #049abf;
      padding: 10px 20px;
      margin-bottom: 40px;
      border-radius: 5px;
      &__title {
        font-size: 25px;
        font-weight: 600;
        color: white;
        margin: 0 !important;
      }
    }

    .btn-container {
      grid-column: full-start / full-end;
      margin-top: 80px;

      display: flex;
      justify-content: space-between;

      div {
        display: flex;
        gap: 40px;
      }

      button {
        background-color: #049abf;
        padding: 8px 30px;
        font-size: 16px;
        border: none;
        border-radius: 3px;
        color: white;
        cursor: pointer;
      }

      .enterprise-info-container {
        display: grid;
        grid-template-columns: [full-start type-start] 20% [type-end field-stat] 80% [field-end full-end];
        grid-template-rows: repeat(7, [row-start] min-content [row-end]);
        grid-gap: 10px 20px;

        @media screen and (max-width: 600px) {
          grid-template-columns: 1fr;
        }
      }

      span {
        display: block;
        font-weight: 300;
      }
    }

    .cofounder-container {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-gap: 40px;

      @media screen and (max-width: 600px) {
        grid-template-columns: 1fr;
      }
    }

    .box {
      display: flex;
      gap: 20px;

      @media screen and (max-width: 600px) {
        flex-direction: column;
        gap: 0;
      }
    }
    .box-8 {
      display: grid;
      grid-template-columns: repeat(2, max-content);
      column-gap: 10rem;

      @media screen and (max-width: 600px) {
        grid-template-columns: 1fr;
        column-gap: 0;
      }
    }
    .sm-box {
      width: 100%;

      @media screen and (max-width: 600px) {
        width: 100%;
      }
    }
    .component {
      display: flex;
      gap: 50px;

      @media screen and (max-width: 600px) {
        gap: 10px;
      }
    }
    .limit {
      font-weight: 300;
    }
    ul {
      margin: 10px 0 20px 0;
    }
    h5 {
      font-size: 15px;
      font-weight: 700;
      margin: 30px 0 10px 0;

      position: relative;
    }
    .required::before {
      content: "*";
      color: red;

      position: absolute;
      left: -10px;
    }

    .co-founder {
      display: grid;
      grid-template-columns: 20% 80%;
      grid-template-rows: repeat(5, min-content);
      grid-gap: 5px 0;

      @media screen and (max-width: 600px) {
        grid-template-columns: 1fr;
      }
    }

    .form-group {
      .btn {
        padding: 5px 10px;
        font-size: 13px;
        font-weight: 500;
        color: white;
        border: none;
        cursor: pointer;
        margin: 5px 0;

        &:hover {
          filter: brightness(90%);
        }
      }
    }
    .pb {
      padding-bottom: 10px !important;
    }
    .mb {
      margin-bottom: 10px;
    }
    .mb-2 {
      margin-bottom: 20px !important;
    }
    .mt {
      margin-top: 10px;
    }
    .no-margin {
      margin: 0;
    }
    .h-align {
      display: flex;
      gap: 20px;
    }

    .option {
      margin: 10px 0;
    }
    .container {
      padding-top: 30px !important;
    }
    .flex-container {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 10rem;

      @media screen and (max-width: 600px) {
        flex-direction: column-reverse;
        gap: 2rem;
      }
    }
    .pitchdeck-error {
      margin-left: 20%;
    }
    .checkbox-option {
      display: flex;
      align-items: center;
      gap: 10px;

      margin-bottom: 10px;
    }

    input[type="text"],
    input[type="url"],
    input[type="tel"],
    input[type="email"] {
      height: 40px;
      border: none;
      font-size: 16px;
      width: 100%;
      padding: 7px;
      border: 2px solid #ffff;

      &:focus {
        outline: 0;
        border: 2px solid #777;
      }
    }
    textarea {
      border: none;
      font-size: 16px;
      width: 100%;
      padding: 7px;
      border: 2px solid #ffff;

      &:focus {
        outline: 0;
        border: 2px solid #777;
      }
    }

    input[type="radio"] {
      margin: 0 3px;
    }

    input[type="file"] {
      padding: 10px 20px;
      background-color: white;
      // width: 100%;
      cursor: pointer;
    }
    .download-btn {
      font-size: 16px;
      padding: 10px 20px;
      line-height: 1.3;
      background-color: #049abf;
      color: #fff;
      text-decoration: none;
    }

    .btn-container {
      display: flex;
      gap: 2rem;

      @media screen and (max-width: 600px) {
        flex-direction: column-reverse;
      }

      input[type="submit"],
      input[type="button"] {
        display: block;
        width: 100%;
        font-size: 16px;
        font-weight: 700;
        color: white;
        background: #049abf;
        border: none;
        border-radius: 3px;
        padding: 10px 20px;
        &:hover {
          filter: brightness(90%);
          cursor: pointer;
        }
      }
    }

    .important-text {
      font-style: italic;
      color: black;
    }
  }
}
.application_info {
  text-align: center;
  color: black;
}
</style>
