<template>
    <div id="application">
        <div class="heading-container">
            <div class="img-container">
                <img src="../assets/images/landing-new-image/yyg-logo/yyg-logo-color.png" alt="YY Goshthi logo">
            </div>
            <div class="heading">
                <span>Spring Cohort 2022</span>
            </div>
        </div>
        <!-- <h1 class="heading"> YY Goshthi Spring {{getCurrentyear()}}</h1> -->
        <form id="form" @submit="submit" >
            <div class="form-heading-container">
                <h1 class="form-heading-container__heading">Application Form</h1>
            </div>
            <div class="enterprise-info-container">
                <div class="enterprise-name">
                    <h5 class="required no-margin">Name of your enterprise</h5>
                </div>
                <div class="enterprise-name-field">
                    <input type="text" v-model="enterpriseName" id="enterpriseName" >
                    <small>error message</small>
                </div>
                <div class="enterprise-summary">
                    <h5 class="required no-margin">Summary of your enterprise <span>(100 words max)</span></h5>
                </div>
                <div class="enterprise-summary-field">
                    <textarea v-model="enterpriseSummary" id="enterpriseSummary" cols="30" rows="8" maxlength="500"></textarea>
                    <small>error message</small>
                </div>
                <div class="enterprise-mission">
                    <h5 class="required no-margin">Mission</h5>
                </div>
                <div class="enterprise-mission-field">
                    <textarea v-model="enterpriseMission" id="enterpriseMission" maxlength="300" cols="50" rows="5"></textarea>
                    <small>error message</small>
                </div>
                <div class="enterprise-vision">
                    <h5 class="required no-margin">Vision</h5>
                </div>
                <div class="enterprise-vision-field">
                    <textarea v-model="enterpriseVision" id="enterpriseVision" maxlength="300" cols="50" rows="5"></textarea>
                    <small>error message</small>
                </div>
                <div class="enterprise-social-media">
                    <h5 class="no-margin">Enterprise Social Media Handle</h5>
                </div>
                <div class="enterprise-social-media-field">
                    <input type="text" v-model="enterpriseSocialMedia" id="enterpriseSocialMedia">
                    <small>error message</small>
                </div>
                <div class="enterprise-website">
                    <h5 class="no-margin">Enterprise Website</h5>
                </div>
                <div class="enterprise-website-field">
                    <input type="text" v-model="enterpriseWebsite" id="enterpriseWebsite">
                    <small>error message</small>
                </div>
            </div>

            <h5 class="required">Do you have a team of minimum two co-founders?</h5>
            <div class="box" id="team">
                <div class="option">
                    <input type="radio" id="team_yes" v-model="team" name="team" value="Team">
                    <label for="team_yes">Yes</label>
                </div>
                <div class="option">
                    <input type="radio" id="team_no" v-model="team" name="team" value="Self">
                    <label for="team_no">No</label>
                </div>
                <small>error message</small>
            </div>
            <p class='important-text'>**To ensure gender equality within our program, we appreciate applications that have at least one female co-founder.</p>
            <p class="important-text">**If you do not have a co-founder now, please add someone from your core team who will be committing to the incubation program.</p>
            <div class="cofounder-container">
                <div class="box-1">
                    <h5 class="required">Co-founder 1</h5>
                    <div class="co-founder">
                        <div class="co-founder__name">
                            <label for="co-founder_1">Name:</label>
                        </div>
                        <div class="co-founder__name-field">
                            <input type="text" id="co-founder_1" v-model="cofounderName1">
                            <small>error message</small>
                        </div>
                        <div class="co-founder__gender">
                            <label>Gender:</label>
                        </div>
                        <div class="co-founder__gender-field">
                            <div class="gender-container" id="gender1">
                                <div class="box">
                                    <div class="option">
                                        <input type="radio" id="male1" class="gender1" v-model="gender1" name="gender1" value="Male">
                                        <label for="male1">Male</label>
                                    </div>
                                    <div class="option">
                                        <input type="radio" id="female1" class="gender1" v-model="gender1" name="gender1" value="Female">
                                        <label for="female1">Female</label>
                                    </div>
                                    <div class="option">
                                        <input type="radio" id="not-prefer1" class="gender1" v-model="gender1" name="gender1" value="Prefer not to say">
                                        <label for="not-prefer1">Prefer not to say</label>
                                    </div>
                                </div>
                                <small>error message</small>
                            </div>
                        </div>
                        <div class="co-founder__email">
                            <label for="email1">Email:</label>
                        </div>
                        <div class="co-founder__email-field">
                            <input type="text" v-model="email1" name="email1" id="email1">
                            <small>error message</small>
                        </div>
                        <div class="co-founder__phone">
                            <label for="tel1">Phone:</label>
                        </div>
                        <div class="co-founder__phone-field">
                            <input type="tel" v-model="phone1" name="tel1" id="tel1">
                            <small>error message</small>
                        </div>
                        <div class="co-founder__linkedin">
                            <label for="linkedin1">LinkedIn:</label>
                        </div>
                        <div class="co-founder__linkedin-field">
                            <input type="text" v-model="linkedin1" name="linkedin1" id="linkedin1">
                            <small>error message</small>
                        </div>
                    </div>
                </div>
                <div class="box-2">
                    <h5 class="required">Co-founder 2</h5>
                    <div class="co-founder">
                        <div class="co-founder__name">
                            <label for="co-founder_2">Name:</label>
                        </div>
                        <div class="co-founder__name-field">
                            <input type="text" id="co-founder_2" v-model="cofounderName2">
                            <small>error message</small>
                        </div>
                        <div class="co-founder__gender">
                            <label>Gender:</label>
                        </div>
                        <div class="co-founder__gender-field">
                            <div class="gender-container" id="gender2">
                                <div class="box">
                                    <div class="option">
                                        <input type="radio" id="male2" class="gender2" v-model="gender2" name="gender2" value="Male">
                                        <label for="male2">Male</label>
                                    </div>
                                    <div class="option">
                                        <input type="radio" id="female2" class="gender2" v-model="gender2" name="gender2" value="Female">
                                        <label for="female2">Female</label>
                                    </div>
                                    <div class="option">
                                        <input type="radio" id="not-prefer2" class="gender2" v-model="gender2" name="gender2" value="Prefer not to say">
                                        <label for="not-prefer2">Prefer not to say</label>
                                    </div>
                                </div>
                                <small>error message</small>
                            </div>
                        </div>
                        <div class="co-founder__email">
                            <label for="email2">Email:</label>
                        </div>
                        <div class="co-founder__email-field">
                            <input type="text" v-model="email2" name="email2" id="email2">
                            <small>error message</small>
                        </div>
                        <div class="co-founder__phone">
                            <label for="tel2">Phone:</label>
                        </div>
                        <div class="co-founder__phone-field">
                            <input type="tel" v-model="phone2" name="tel2" id="tel2">
                            <small>error message</small>
                        </div>
                        <div class="co-founder__linkedin">
                            <label for="linkedin2">LinkedIn:</label>
                        </div>
                        <div class="co-founder__linkedin-field">
                            <input type="url" v-model="linkedin2" name="linkedin2" id="linkedin2">
                            <small>error message</small>
                        </div>
                    </div>
                </div>

            </div>


            <h5 class="required">Does your enterprise work to reduce any of the following:</h5>
            <div class="box-1" id="reduceProblems">
                <div class="checkbox-option">
                    <input type="checkbox" name="reduce" id="carbon-emission" class="reduce" v-model="reduceProblem" value="Carbon emission">
                    <label for="carbon-emission">Carbon emission</label>
                </div>
                <div class="checkbox-option">
                    <input type="checkbox" name="reduce" id="unemployment" class="reduce" v-model="reduceProblem" value="Unemployment">
                    <label for="unemployment">Unemployment</label>
                </div>
                <div class="checkbox-option">
                    <input type="checkbox" name="reduce" id="poverty" class="reduce" v-model="reduceProblem" value="Poverty">
                    <label for="poverty">Poverty</label>
                </div>
                <div class="checkbox-option">
                    <input type="checkbox" name="reduce" id="none" class="reduce" v-model="reduceProblem" value="None of the above">
                    <label for="none">None of the above</label>
                </div>
                <small>error message</small>
            </div>
            
            <h5>If yes, how is your enterprise reducing carbon emission, creating jobs or fighting poverty? <span class="limit">(100 words max)</span></h5>
            <div class="box">
                <textarea name="reducing" id="howEnterpriseReduce" v-model="howEnterpriseReduce" maxlength="500" cols="30" rows="8"></textarea>
                <small>error message</small>

            </div>
        
            <h5 class="required">Do you know how to measure the impact of your work?</h5>
            <div class="box" id="measure">
                <div class="option">
                    <input type="radio" id="measure_yes" class="measure" v-model="impactMeasure" name="measure" value="1">
                    <label for="measure_yes">Yes</label>
                </div>
                <div class="option">
                    <input type="radio" id="measure_no" class="measure" v-model="impactMeasure" name="measure" value="0">
                    <label for="measure_no">No</label>
                </div>
                <small>error message</small>
            </div>

            <h5>If yes, please tell us what methodology you use. <span class="limit">(100 words max)</span></h5>
            <textarea v-model="methodology" maxlength="500" cols="30" rows="8"></textarea>

            <h5 class="required">What innovation is your enterprise bringing to the local market? <span class="limit">(100 words max)</span></h5>
            <div class="innovation-field">
                <textarea id="enterpriseInnovation" v-model="enterpriseInnovation" maxlength="500" cols="30" rows="8"></textarea>
                <small>error message</small>
            </div>

            <h5 class="required">We respect and welcome both product and process innovation offered by enterprises and we would love to know more about your enterprise’s innovation. <span class="limit">(100 words max)</span></h5>
            <div class="innovation-field">
                <textarea id="enterpriseInnovationMore" v-model="enterpriseInnovationMore" maxlength="500" cols="30" rows="8"></textarea>
                <small>error message</small>
            </div>

            <h5 class="required">What is the stage of your venture?</h5>
            <div class="box-1" id="ventureStage">
                <div class="box">
                    <div class="option">
                        <input type="radio" class="stage-venture" id="idea_stage" v-model="stage" name="stage" value="Idea Stage">
                        <label for="idea_stage">Idea Stage</label>
                    </div>
                    <div class="option">
                        <input type="radio" class="stage-venture" id="pilot_stage" v-model="stage" name="stage" value="Feasibility/Prototype/Pilot Stage">
                        <label for="pilot_stage">Feasibility/Prototype/Pilot Stage</label>
                    </div>
                    <div class="option">
                        <input type="radio" class="stage-venture" id="growth_stage" v-model="stage" name="stage" value="Growth Stage">
                        <label for="growth_stage">Growth Stage</label>
                    </div>
                </div>
                <small>error message</small>
            </div>

            <h5 class="required">Is the enterprise registered as an entity under the law of Bangladesh?</h5>
            <div class="box-1" id="registered">
                <div class="box">
                    <div class="option">
                        <input type="radio" class="registered" id="registered_yes" v-model="registered" name="registered" value="1">
                        <label for="registered_yes">Yes</label>
                    </div>
                    <div class="option">
                        <input type="radio" class="registered" id="registered_no" v-model="registered" name="registered" value="0">
                        <label for="registered_no">No</label>
                    </div>
                </div>
                <small>error message</small>
            </div>
            <h5 class="mt">If yes, what is the legal status of your venture?</h5>
            <div class="box-1">
                <div class="box">
                    <div class="option">
                        <input type="radio" id="limited-company" v-model="legalStatus" name="legalStatus" value="For profit/Limited company">
                        <label for="limited-company">For profit/Limited company</label>
                    </div>
                    <div class="option">
                        <input type="radio" id="ngo-company" v-model="legalStatus" name="legalStatus" value="Non profit/NGO/Foundation">
                        <label for="ngo-company">Non profit/NGO/Foundation</label>
                    </div>
                    <div class="option">
                        <input type="radio" id="sole-proprietorship" v-model="legalStatus" name="legalStatus" value="Sole proprietorship">
                        <label for="sole-proprietorship">Sole proprietorship</label>
                    </div>
                </div>
                <div class="option h-align">
                    <label for="other">Other: </label>
                    <input type="text" id="other" v-model="legalStatusOther">
                </div>
                <small>error message</small>
            </div>

            <h5 class="required">How does your enterprise make money? <span class="limit">(100 words max)</span></h5>
            <div class="box-1">
                <textarea id="enterpriseMakeMoney" v-model="enterpriseMakeMoney" maxlength="500" cols="30" rows="8"></textarea>
                <small>error message</small>
            </div>

            <h5 class="required">How much revenue do you have at the moment (in BDT)?</h5>
            <div class="box-1" id="revenueGenerate">
                <div class="option">
                    <input type="radio" class="revenueAmount" id="revenue-a" v-model="revenue" name="revenue" value="0 - 100000">
                    <label for="revenue-a">0 - 100000</label>
                </div>
                <div class="option">
                    <input type="radio" class="revenueAmount" id="revenue-b" v-model="revenue" name="revenue" value="100000 - 500000">
                    <label for="revenue-b">100000 - 500000</label>
                </div>
                <div class="option">
                    <input type="radio" class="revenueAmount" id="revenue-c" v-model="revenue" name="revenue" value="500000 - 2000000">
                    <label for="revenue-c">500000 - 2000000</label>
                </div>
                <div class="option">
                    <input type="radio" class="revenueAmount" id="revenue-d" v-model="revenue" name="revenue" value="2000000 - 5000000">
                    <label for="revenue-d">2000000 - 5000000</label>
                </div>
                <div class="option">
                    <input type="radio" class="revenueAmount" id="revenue-e" v-model="revenue" name="revenue" value="> 5000000">
                    <label for="revenue-e">> 5000000</label>
                </div>
                <small>error message</small>
            </div>

            <h5 class="required">How many customers are you serving right now?</h5>
            <div class="box-1" id="customerAmount">
                <div class="option">
                    <input type="radio" id="customers-a" v-model="customers" name="customers" value="0 - 100">
                    <label for="customers-a">0 - 100</label>
                </div>
                <div class="option">
                    <input type="radio" id="customers-b" v-model="customers" name="customers" value="100 - 1000">
                    <label for="customers-b">100 - 1000</label>
                </div>
                <div class="option">
                    <input type="radio" id="customers-c" v-model="customers" name="customers" value="1000 - 10000">
                    <label for="customers-c">1000 - 10000</label>
                </div>
                <div class="option">
                    <input type="radio" id="customers-d" v-model="customers" name="customers" value="> 10000">
                    <label for="customers-d">> 10000</label>
                </div>
                <small>error message</small>
            </div>

            <h5>Please share any media link where your enterprise has been featured</h5>
            <div class="media-link-group">
                <input type="url" v-model="media_link_1" id="media_link_1" name="media-link" placeholder="link 1" class="mb">
                <input type="url" v-model="media_link_2" id="media_link_2" name="media-link" placeholder="link 2" class="mb">
                <input type="url" v-model="media_link_3" id="media_link_3" name="media-link" placeholder="link 3" class="mb">
                <input type="url" v-model="media_link_4" id="media_link_4" name="media-link" placeholder="link 4" class="mb">
                <small>error message</small>
            </div>

            <div class="sm-box">
                <h5 class="required">Please upload your pitch deck</h5>
                <p class='important-text'>**Your pitch deck will be provided with your full application to the panel of judges. Please make sure your pitch deck has the following components:</p>
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
                    <input type="file" id="pitchDeck" class="mb" @change='handleFileUpload' name="pitch_deck" >
                    <small>error message</small>
                </div>
                <div class="btn-container">
                    <input type="submit" id="submitButton">
                    <input type="button" @click="saveAsDraft" id="draftButton" value="save as draft">
                </div>
            </div>
        </form>
        <div v-if="this.show_message">
            <SuccessPopup/>
        </div>
        <div v-if="this.show_draft_success_message">
            <SuccessDraftPopup/>
        </div>
    </div>
</template>

<script>
    // import { post } from '@/assets/scripts/api';
    import axios from 'axios'
    import SuccessPopup from '../components/landing-page-new/components/SuccessPopup.vue'
    import SuccessDraftPopup from '../components/landing-page-new/components/SuccessDraftPopup.vue'

    export default {
        components: {
            SuccessPopup,
            SuccessDraftPopup
        },
        data() {
            return {
                enterpriseName: '',
                enterpriseSummary: '',
                enterpriseMission: '',
                enterpriseVision: '',
                enterpriseSocialMedia: '',
                enterpriseWebsite: '',
                team: '',
                cofounderName1: '',
                gender1: '',
                email1: '',
                phone1: '',
                linkedin1: '',
                cofounderName2: '',
                gender2: '',
                email2: '',
                phone2: '',
                linkedin2: '',
                reduceProblem: [],
                howEnterpriseReduce: '',
                impactMeasure : '',
                methodology: '',
                enterpriseInnovation: '',
                enterpriseInnovationMore: '',
                stage: '',
                registered: '',
                legalStatus: '',
                legalStatusOther: '',
                enterpriseMakeMoney: '',
                revenue: '',
                customers: '',
                media_link_1: '',
                media_link_2: '',
                media_link_3: '',
                media_link_4: '',
                year: '2022',
                season: 'Spring',
                file: '',
                checkFile: '',
                show_message: false,
                show_draft_success_message: false,
                errors:[],
                submission: false,
                draft: false

            }
        },
        mounted: function() {
            const draftData = localStorage.getItem('draftData');
            // this.enterpriseName = draftData.name_of_business;
            // this.enterpriseSummary = draftData.summery_of_experience;
            // this.enterpriseMission = draftData.mission;
            // this.enterpriseVision = draftData.vision;
            // this.enterpriseSocialMedia = draftData.enterprise_social_media;
            // this.enterpriseWebsite = draftData.enterprise_website;
            // this.team = draftData.founder_type;

            // this.cofounderName1 = draftData.co_founder_name_one;
            // this.gender1 = draftData.co_founder_gender_one;
            // this.email1 = draftData.co_founder_email_one;
            // this.phone1 = draftData.co_founder_mobile_one;
            // this.linkedin1 = draftData.co_founder_linkedin_one;

            // this.cofounderName2 = draftData.co_founder_name_two;
            // this.gender2 = draftData.co_founder_gender_two;
            // this.email2 = draftData.co_founder_email_two;
            // this.phone2 = draftData.co_founder_mobile_two;
            // this.linkedin2 = draftData.co_founder_linkedin_two;

            // this.reduceProblem = draftData.reduce_problem;
            // this.howEnterpriseReduce = draftData.reduce_problem_process;
            // this.impactMeasure = draftData.is_known_impact_of_work;
            // this.methodology = draftData.methodology_of_work;
            // this.enterpriseInnovation = draftData.innovation;
            // this.enterpriseInnovationMore = draftData.experience_of_innovation;
            // this.revenue = draftData.current_revenue_range;
            // this.customers = draftData.enterprise_website;
            // this.enterpriseWebsite = draftData.customer_range;
            // this.media_link_1 = draftData.media_links[0];
            // this.media_link_2 = draftData.media_links[1];
            // this.media_link_3 = draftData.media_links[2];
            // this.media_link_4 = draftData.media_links[3];
            // this.file = draftData.pitch_deck;
        },
   
        methods: {
             setFormData: function() {
                const data = new FormData();
                data.set('name_of_business',this.enterpriseName);//
                data.set('summery_of_experience',this.enterpriseSummary);//
                data.set('mission',this.enterpriseMission);//
                data.set('vision',this.enterpriseVision);//
                data.set('enterprise_social_media',this.enterpriseSocialMedia);
                data.set('enterprise_website',this.enterpriseWebsite);
                data.set('founder_type',this.team);//
                data.set('co_founder_name_one',this.cofounderName1);//
                data.set('co_founder_gender_one',this.gender1);//
                data.set('co_founder_email_one',this.email1);//
                data.set('co_founder_mobile_one',this.phone1);//
                data.set('co_founder_linkedin_one',this.linkedin1);
                data.set('co_founder_name_two',this.cofounderName2);//
                data.set('co_founder_gender_two',this.gender2);//
                data.set('co_founder_email_two',this.email2);//
                data.set('co_founder_mobile_two',this.phone2);//
                data.set('co_founder_linkedin_two',this.linkedin2);
                data.set('reduce_problem',this.reduceProblem.toString());
                data.set('reduce_problem_process',this.howEnterpriseReduce);
                data.set('is_known_impact_of_work',this.impactMeasure);
                data.set('methodology_of_work',this.methodology);
                data.set('innovation',this.enterpriseInnovation);//
                data.set('experience_of_innovation',this.enterpriseInnovationMore);
                data.set('stage_of_ventures',this.stage);//
                data.set('is_registered_under_law',this.registered);//
                data.set('legal_status_ventures',this.legalStatusOption());
                data.set('make_money_plan', this.enterpriseMakeMoney)//
                data.set('current_revenue_range',this.revenue);
                data.set('customer_range',this.customers);
                data.set('media_links',[this.media_link_1, this.media_link_2, this.media_link_3, this.media_link_4]);
                data.set('year',this.year);
                data.set('season',this.season);
                data.set('pitch_deck', this.file);//
                data.set('submission_type', this.submissionType());

                return data;
            },

            submit: async function (e) {
                const success= this.checkInput(e);

                // Form Data
                const data = this.setFormData();
                
                console.log('success', success)
                if(success){
                    this.disableSubmitButton();
                    this.disableDraftButton();
                    axios.post('https://yyv.yyventures.org/api/yyg-application-submit-form/create', data)
                    .then(response => {
                        if (response.status == 200) {
                        this.show_message = true;
                        };
                    })
                    .catch(error => {
                        console.log(error)
                    })
                }               
            },
           
            saveAsDraft: async function(e){
                const success = this.checkDraftMinInput(e);

                console.log('in draft function')

                // Form Data
                const data = this.setFormData();
                console.log('success', success)

                if(success){
                    this.disableSubmitButton();
                    this.disableDraftButton();
                    const response = await axios.post('https://yyv.yyventures.org/api/yyg-application-submit-form/create', data);

                    console.log(response);

                    try {
                        if(response.status == 200){
                            this.show_draft_success_message = true;
                        }
                    } catch (err) {
                        console.log(err);
                    }
                }

            },

            disableSubmitButton: function(){
                console.log('in function')
                const submitBtn = document.querySelector('#submitButton');
                submitBtn.disabled = true;
                submitBtn.style.opacity = '0.4';
                submitBtn.style.cursor = 'wait';
            },
            disableDraftButton: function(){
                const draftBtn = document.querySelector('#draftButton');
                draftBtn.disabled = true;
                draftBtn.style.opacity = '0.4';
                draftBtn.style.cursor = 'wait';
            },
                    
            getCurrentyear: function(){
                const date = new Date();
                const year = date.getFullYear();
                this.year = year;
            },
            handleFileUpload: function(e){     
                this.checkFile = e.target.files[0];
                if(this.checkFile.size > 5242880){
                    alert(`Please upload your file between 5MB, your file is ${Math.round(this.checkFile.size / 1048576)}MB`)
                    e.target.value = '';
                }else{
                    this.file = this.checkFile;
                }

            },
            checkInput: function(e){
                e.preventDefault()
                const enterpriseName = document.querySelector('#enterpriseName');
                const enterpriseSummary = document.querySelector('#enterpriseSummary');
                const enterpriseMission = document.querySelector('#enterpriseMission');
                const enterpriseVision = document.querySelector('#enterpriseVision');
                const enterpriseSocialMedia = document.querySelector('#enterpriseSocialMedia');
                const enterpriseWebsite = document.querySelector('#enterpriseWebsite');
                const team = document.querySelector('#team');
                const cofounderName1 = document.querySelector('#co-founder_1');
                const gender1 = document.querySelector('#gender1');
                const email1 = document.querySelector('#email1');
                const phone1 = document.querySelector('#tel1');
                const linkedin1 = document.querySelector('#linkedin1');
                const cofounderName2 = document.querySelector('#co-founder_2');
                const gender2 = document.querySelector('#gender2');
                const email2 = document.querySelector('#email2');
                const phone2 = document.querySelector('#tel2');
                const linkedin2 = document.querySelector('#linkedin2');
                const reduceProblem = document.querySelector('#reduceProblems');
                const impactMeasure = document.querySelector('#measure');
                const enterpriseInnovation = document.querySelector('#enterpriseInnovation');
                const enterpriseInnovationMore = document.querySelector('#enterpriseInnovationMore');
                const stageVenture = document.querySelector('#ventureStage');
                const registered = document.querySelector('#registered');
                const enterpriseMakeMoney = document.querySelector('#enterpriseMakeMoney');
                const revenueAmount = document.querySelector('#revenueGenerate');
                const customerAmount = document.querySelector('#customerAmount');
                const mediaLink1 = document.querySelector('#media_link_1');
                const mediaLink2 = document.querySelector('#media_link_2');
                const mediaLink3 = document.querySelector('#media_link_3');
                const mediaLink4 = document.querySelector('#media_link_4');
                const pitchDeck = document.querySelector('#pitchDeck');


                let error = false;
                if(this.enterpriseName === ''){
                    this.setErrorFor(enterpriseName, 'Enterprise name cannot be empty')
                    error = true;
                    
                }else{
                    this.setSuccessFor(enterpriseName)
                }
                if(this.enterpriseSummary === ''){
                    this.setErrorFor(enterpriseSummary, 'Enterprise summary cannot be empty')
                    error = true
                    
                }else{
                    this.setSuccessFor(enterpriseSummary)
                }
                if(this.enterpriseMission === ''){
                    this.setErrorFor(enterpriseMission, 'Enterprise mission cannot be empty')
                    error = true
                    
                }else{
                    this.setSuccessFor(enterpriseMission)
                }
                if(this.enterpriseVision === ''){
                    this.setErrorFor(enterpriseVision, 'Enterprise vision cannot be empty')
                    error = true
                    
                }else{
                    this.setSuccessFor(enterpriseVision)
                }
                console.log(this.enterpriseSocialMedia)
                if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.enterpriseSocialMedia)){
                    this.setErrorFor(enterpriseSocialMedia, 'Should be an URL')
                    error = true
                    console.log(this.enterpriseSocialMedia)              
                }else{
                    this.setSuccessFor(enterpriseSocialMedia)
                }
                if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.enterpriseWebsite)){
                    this.setErrorFor(enterpriseWebsite, 'Should be an URL')
                    error = true                    
                }else{
                    this.setSuccessFor(enterpriseWebsite)
                }

                if(this.team === ''){
                    this.setErrorForTeam('Choose any option')
                    error = true                    
                }else{
                    this.setSuccessFor(team)
                }

                if(this.cofounderName1 === ''){
                    this.setErrorFor(cofounderName1, 'Co-founder name cannot be empty')
                    error = true
                    
                }else{
                    this.setSuccessFor(cofounderName1)
                }
                if(this.gender1 === ''){
                    this.setErrorForGender1('Choose an option')
                    error = true
                    
                }else{
                    this.setSuccessFor(gender1)
                }
                if(this.email1 === ''){
                    this.setErrorFor(email1, 'email cannot be empty')
                    error = true
                } else if (!/^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i.test(this.email1)) {
		            this.setErrorFor(email1, 'Not a valid email');
                }else{
                    this.setSuccessFor(email1)
                }
                if(this.phone1 === ''){
                    this.setErrorFor(phone1, 'Phone number cannot be empty')
                    error = true
                }else if(!/[0-9]+/.test(this.phone1)){
                    this.setErrorFor(phone1, 'invalid number')
                    error = true
                }else{
                    this.setSuccessFor(phone1)
                }

                if(this.linkedin1 === ''){
                    this.setErrorFor(linkedin1, 'link cannot be empty')
                    error = true                    
                }else if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.linkedin1)){
                    this.setErrorFor(linkedin1, 'Not a valid URL')
                    error = true
                }else{                        
                    this.setSuccessFor(linkedin1)
                }

                if(this.cofounderName2 === ''){
                    this.setErrorFor(cofounderName2, 'Co-founder name cannot be empty')
                    error = true
                    
                }else{
                    this.setSuccessFor(cofounderName2)
                }
                
                if(this.gender2 === ''){
                    this.setErrorForGender2('Choose an option')
                    error = true
                    
                }else{
                    this.setSuccessFor(gender2)
                }
                if(this.email2 === ''){
                    this.setErrorFor(email2, 'email cannot be empty')
                    error = true
                } else if (!/^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i.test(this.email2)) {
                    this.setErrorFor(email2, 'Not a valid email');
                    error = true
                }else{
                    this.setSuccessFor(email2)

                }
                if(this.phone2 === ''){
                    this.setErrorFor(phone2, 'Phone number cannot be empty')
                    error = true
                    
                }else if(!/[0-9]+/.test(this.phone2)){
                    this.setErrorFor(phone2, 'invalid number')
                    error = true
                }
                else{
                    this.setSuccessFor(phone2)
                }

                if(this.linkedin2 === ''){
                    this.setErrorFor(linkedin2, 'link cannot be empty')
                    error = true
                }else if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.linkedin2)){
                    this.setErrorFor(linkedin1, 'Not a valid URL')
                    error = true
                }else{
                    this.setSuccessFor(linkedin2)
                }

                if(this.reduceProblem.length <= 0){
                    this.setErrorReduceProblem('Choose any option')
                    error = true                    
                }else{
                    this.setSuccessFor(reduceProblem)
                }

                if(this.impactMeasure === ''){
                    this.setErrorForMeasure('Choose any option')
                    error = true                    
                }else{
                    this.setSuccessFor(impactMeasure)
                }

                if(this.enterpriseInnovation === ''){
                    this.setErrorFor(enterpriseInnovation, 'field cannot be empty')
                    error = true                    
                }else{
                    this.setSuccessFor(enterpriseInnovation)
                }

                if(this.enterpriseInnovationMore === ''){
                    this.setErrorFor(enterpriseInnovationMore, 'field cannot be empty')
                    error = true                    
                }else{
                    this.setSuccessFor(enterpriseInnovationMore)
                }

                if(this.stage === ''){
                    this.setErrorForVentureStage('Choose any option')
                    error = true
                }else{
                    this.setSuccessFor(stageVenture)
                }

                if(this.registered === ''){
                    this.setErrorForRegistered('Choose any option')
                    error = true
                }else{
                    this.setSuccessFor(registered)
                }

                if(this.enterpriseMakeMoney === ''){
                    this.setErrorFor(enterpriseMakeMoney, 'field cannot be empty')
                    error = true
                }else{
                    this.setSuccessFor(enterpriseMakeMoney)
                }

                if(this.revenue === ''){
                    this.setErrorForRevenue('Choose any option')
                    error = true
                }else{
                    this.setSuccessFor(revenueAmount)
                }

                if(this.customers === ''){
                    this.setErrorForCustomers('Choose any option')
                    error = true
                }else{
                    this.setSuccessFor(customerAmount)
                }
                if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.media_link_1)){
                    this.setErrorFor(mediaLink1, 'Not a valid URL')
                    error = true
                }else{
                    this.setSuccessFor(mediaLink1)
                }
                if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.media_link_2)){
                    this.setErrorFor(mediaLink2, 'Not a valid URL')
                    error = true
                }else{
                    this.setSuccessFor(mediaLink2)
                }
                if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.media_link_3)){
                    this.setErrorFor(mediaLink3, 'Not a valid URL')
                    error = true
                }else{
                    this.setSuccessFor(mediaLink3)
                }
                if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.media_link_4)){
                    this.setErrorFor(mediaLink4, 'Not a valid URL')
                    error = true
                }else{
                    this.setSuccessFor(mediaLink4)
                }
                if(this.file === ''){
                    this.setErrorFor(pitchDeck, 'Please upload your pitch deck')
                    error = true
                }else{
                    this.setSuccessFor(pitchDeck)
                }
                return !error
            },
            checkDraftMinInput: function(e){
                e.preventDefault()
                const enterpriseName = document.querySelector('#enterpriseName');
                const enterpriseSummary = document.querySelector('#enterpriseSummary');
                const enterpriseMission = document.querySelector('#enterpriseMission');
                const enterpriseVision = document.querySelector('#enterpriseVision');
                const enterpriseSocialMedia = document.querySelector('#enterpriseSocialMedia');
                const enterpriseWebsite = document.querySelector('#enterpriseWebsite');
                const team = document.querySelector('#team');
                const cofounderName1 = document.querySelector('#co-founder_1');
                const gender1 = document.querySelector('#gender1');
                const email1 = document.querySelector('#email1');
                const phone1 = document.querySelector('#tel1');
                const linkedin1 = document.querySelector('#linkedin1');
                const cofounderName2 = document.querySelector('#co-founder_2');
                const gender2 = document.querySelector('#gender2');
                const email2 = document.querySelector('#email2');
                const phone2 = document.querySelector('#tel2');
                const linkedin2 = document.querySelector('#linkedin2');

                let error = false;
                if(this.enterpriseName === ''){
                    this.setErrorFor(enterpriseName, "Enterprise name cannot be empty for draft" )
                    error=true;
                }else{
                    this.setSuccessFor(enterpriseName)
                }
                if(this.enterpriseSummary === ''){
                    this.setErrorFor(enterpriseSummary, 'Enterprise summary cannot be empty for draft')
                    error = true
                    
                }else{
                    this.setSuccessFor(enterpriseSummary)
                }
                if(this.enterpriseMission === ''){
                    this.setErrorFor(enterpriseMission, 'Enterprise mission cannot be empty for draft')
                    error = true
                    
                }else{
                    this.setSuccessFor(enterpriseMission)
                }
                if(this.enterpriseVision === ''){
                    this.setErrorFor(enterpriseVision, 'Enterprise vision cannot be empty for draft')
                    error = true
                    
                }else{
                    this.setSuccessFor(enterpriseVision)
                }
                console.log(this.enterpriseSocialMedia)
                if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.enterpriseSocialMedia)){
                    this.setErrorFor(enterpriseSocialMedia, 'Should be an URL')
                    error = true
                    console.log(this.enterpriseSocialMedia)              
                }else{
                    this.setSuccessFor(enterpriseSocialMedia)
                }
                if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.enterpriseWebsite)){
                    this.setErrorFor(enterpriseWebsite, 'Should be an URL')
                    error = true                    
                }else{
                    this.setSuccessFor(enterpriseWebsite)
                }

                if(this.team === ''){
                    this.setErrorForTeam('Choose any option')
                    error = true                    
                }else{
                    this.setSuccessFor(team)
                }

                if(this.cofounderName1 === ''){
                    this.setErrorFor(cofounderName1, 'Co-founder name cannot be empty for draft')
                    error = true
                    
                }else{
                    this.setSuccessFor(cofounderName1)
                }
                if(this.gender1 === ''){
                    this.setErrorForGender1('Choose an option')
                    error = true
                    
                }else{
                    this.setSuccessFor(gender1)
                }
                if(this.email1 === ''){
                    this.setErrorFor(email1, 'email cannot be empty for draft')
                    error = true
                } else if (!/^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i.test(this.email1)) {
		            this.setErrorFor(email1, 'Not a valid email');
                }else{
                    this.setSuccessFor(email1)
                }
                if(this.phone1 === ''){
                    this.setErrorFor(phone1, 'Phone number cannot be empty for draft')
                    error = true
                }else if(!/[0-9]+/.test(this.phone1)){
                    this.setErrorFor(phone1, 'invalid number')
                    error = true
                }else{
                    this.setSuccessFor(phone1)
                }

                if(this.linkedin1 === ''){
                    this.setErrorFor(linkedin1, 'link cannot be empty for draft')
                    error = true                    
                }else if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.linkedin1)){
                    this.setErrorFor(linkedin1, 'Not a valid URL')
                    error = true
                }else{                        
                    this.setSuccessFor(linkedin1)
                }

                if(this.cofounderName2 === ''){
                    this.setErrorFor(cofounderName2, 'Co-founder name cannot be empty for draft')
                    error = true
                    
                }else{
                    this.setSuccessFor(cofounderName2)
                }
                
                if(this.gender2 === ''){
                    this.setErrorForGender2('Choose an option')
                    error = true
                    
                }else{
                    this.setSuccessFor(gender2)
                }
                if(this.email2 === ''){
                    this.setErrorFor(email2, 'email cannot be empty for draft')
                    error = true
                } else if (!/^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i.test(this.email2)) {
                    this.setErrorFor(email2, 'Not a valid email');
                    error = true
                }else{
                    this.setSuccessFor(email2)

                }
                if(this.phone2 === ''){
                    this.setErrorFor(phone2, 'Phone number cannot be empty for draft')
                    error = true
                    
                }else if(!/[0-9]+/.test(this.phone2)){
                    this.setErrorFor(phone2, 'invalid number')
                    error = true
                }
                else{
                    this.setSuccessFor(phone2)
                }

                if(this.linkedin2 === ''){
                    this.setErrorFor(linkedin2, 'link cannot be empty for draft')
                    error = true
                }else if(!/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)/.test(this.linkedin2)){
                    this.setErrorFor(linkedin1, 'Not a valid URL')
                    error = true
                }else{
                    this.setSuccessFor(linkedin2)
                }
                return !error;
            },
            legalStatusOption: function(){
                if (this.legalStatus === ''){
                    return this.legalStatusOther
                }
                return this.legalStatus
            },
            submissionType: function(){

            },
            setErrorForGender1: function(message){
                const formControl = document.querySelector('#gender1');
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setErrorForGender2: function(message){
                const formControl = document.querySelector('#gender2');
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setErrorForRegistered: function(message){
                const formControl = document.querySelector('#registered');
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setErrorForTeam: function(message){
                const formControl = document.querySelector('#team');
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setErrorForMeasure: function(message){
                const formControl = document.querySelector('#measure');
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setErrorForVentureStage: function(message){
                const formControl = document.querySelector('#ventureStage');
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setErrorForCustomers: function(message){
                const formControl = document.querySelector('#customerAmount');
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setErrorForRevenue: function(message){
                const formControl = document.querySelector('#revenueGenerate');
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setErrorFor: function(input, message){
                const formControl = input.parentElement;
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setSuccessFor: function (input) {
                const formControl = input.parentElement;
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control success';
                small.innerText = '';
            },
            setErrorReduceProblem: function(message){
                const formControl = document.querySelector('#reduceProblems');
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setErrorStage: function(message){
                const formControl = document.querySelector('.stageVenture');
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            }
        },
        
        }

</script>

<style lang="scss" scoped>
    #application{
        position: relative;
        padding: 10rem 5rem;

        @media screen and (max-width: 600px){
            padding: 8rem 0;
        }

        .heading-container{
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 10px;
            margin-bottom: 80px;
            width: min-content;
            margin-inline: auto;

            @media screen and (max-width: 600px){
                padding: 0 20px;
            }
            .img-container{
                height: 100px;

                @media screen and (max-width: 600px){
                    height: 70px;
                }
                img{
                    height: 100%;
                    object-fit: contain;
                }
            }
            .heading{
                span{
                    display: block;
                    color: #3A3A3A;
                    font-size: 36.5px;
                    line-height: 1.2;
                    white-space: nowrap;
                    text-transform: uppercase;
                    font-weight: 300;

                    border-block: 2px solid #3A3A3A;

                    @media screen and (max-width: 600px){
                        font-size: 25px;
                        font-weight: 400;
                    }
                }
            }
        }

        form{
            // border: 1px solid black;
            padding: 80px 70px;
            background-color: #E0EEF2;
            border-radius: 15px;

            position: relative;

            @media screen and (max-width: 600px){
                padding: 50px 40px;
                border-radius: 0;
            }

            .form-heading-container{
                background-color: #EFD214;
                border-radius: 50px;
                padding: 5px 30px;
                width: min-content;

                position: absolute;
                left: 50%;
                top: -20px;
                transform: translate(-50%);
                &__heading{
                    white-space: nowrap;
                    margin: 0;
                    font-size: 30px !important;
                }
            }
            small{
                display: block;
                white-space: nowrap;
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
            .gender-container small{
                color: #e74c3c;
                visibility: hidden;
            }
            .form-control.error small {
                color: #e74c3c;
                visibility: visible;
            }

            .enterprise-info-container{
                display: grid;
                grid-template-columns: [type-start] 20% [type-end field-stat] 80% [field-end];
                grid-template-rows: repeat(6, [row-start] min-content [row-end]);
                grid-gap: 10px 20px;

                @media screen and (max-width: 600px){
                    grid-template-columns: 1fr;
                }

                span{
                    display: block;
                    font-weight: 300;
                }
            }

            .cofounder-container{

                display: grid;
                grid-template-columns: repeat(2, 1fr);
                grid-gap: 40px;

                @media screen and (max-width: 600px){
                    grid-template-columns: 1fr;
                }
            }

            .box{
                display: flex;
                gap: 20px;

                @media screen and (max-width: 600px){
                    flex-direction: column;
                    gap: 0;
                }
            }
            .sm-box{
                width: 70%;

                @media screen and (max-width: 600px){
                    width: 100%;
                }
            }
            .component{
                display: flex;
                gap: 50px;

                @media screen and (max-width: 600px){
                    gap: 10px;
                }
            }
            .limit{
                font-weight: 300;
            }
            ul{
                margin: 10px 0 20px 0;
            }
            h5{
                font-size: 15px;
                font-weight: 700;
                margin: 30px 0 10px 0;

                position: relative;
            }
            .required::before{
                content: '*';
                color: red;

                position: absolute;
                left: -10px;
            }
            
            .co-founder{
                display: grid;
                grid-template-columns: 20% 80%;
                grid-template-rows: repeat(5, min-content);
                grid-gap: 5px 0;

                @media screen and (max-width: 600px){
                    grid-template-columns: 1fr;
                }
            }

            .form-group{
                .btn{
                    padding: 5px 10px;
                    font-size: 13px;
                    font-weight: 500;
                    color: white;
                    border: none;
                    cursor: pointer;
                    margin: 5px 0;

                    &:hover{
                        filter: brightness(90%);
                    }
                }
            }
            .pb{
                padding-bottom: 10px !important;
            }
            .mb{
                margin-bottom: 10px;
            }
            .mb-2{
                margin-bottom: 20px !important;
            }
            .mt{
                margin-top: 10px;                
            }
            .no-margin{
                margin: 0;
            }
            .h-align{
                display: flex;
                gap: 20px;
            }

            .option{
                margin: 10px 0;
            }
            .checkbox-option{
                display: flex;
                align-items: center;
                gap: 10px;

                margin-bottom: 10px;
            }
    
            input[type='text'],
            input[type='url'],
            input[type='tel'],
            input[type='email']
            {
                height: 40px;
                border: none;
                font-size: 16px;
                width: 100%;
                padding: 7px;
                border: 2px solid #ffff;

                &:focus{
                    outline: 0;
                    border: 2px solid #777;
                }
            }
            textarea{
                border: none;
                font-size: 16px;
                width: 100%;
                padding: 7px;
                border: 2px solid #ffff;

                &:focus{
                    outline: 0;
                    border: 2px solid #777;
                }
            }

            input[type='radio']{
                margin: 0 3px;
            }

            input[type='file']{
                padding: 10px 20px;
                background-color: white;
                width: 100%;
                cursor: pointer;
            }

            .btn-container{

                display: flex;
                gap: 2rem;

                input[type='submit'],
                input[type='button']{
                    display: block;
                    width: 100%;
                    font-size: 20px;
                    font-weight: 700;
                    color: white;
                    background: #049abf;
                    border: none;
                    padding: 10px 20px;
                    &:hover{
                        filter: brightness(90%);
                        cursor: pointer;
                    }
                }
            }


            .important-text{
                font-style: italic;
                color: #1e87f0;
            }
        }

    }
</style>