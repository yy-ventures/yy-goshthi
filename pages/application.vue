<template>
    <div id="application">
        <div class="heading-container">
            <div class="img-container">
                <img src="../assets/images/landing-new-image/yyg-logo/yyg-logo-color.png" alt="YY Goshthi logo">
            </div>
            <div class="heading">
                <span class="season">Spring Cohort</span>
                <span class="date">2022</span>
            </div>
        </div>
        <!-- <h1 class="heading"> YY Goshthi Spring {{getCurrentyear()}}</h1> -->
        <form @submit.prevent="submit()">
            <div class="form-heading-container">
                <h1 class="form-heading-container__heading">Application Form</h1>
            </div>
            <div class="enterprise-info-container">
                <div class="enterprise-name">
                    <h5 class="required no-margin">Name of your enterprise</h5>
                </div>
                <div class="enterprise-name-field">
                    <input type="text" v-model="enterpriseName" required>
                </div>
                <div class="enterprise-summary">
                    <h5 class="required no-margin">Summary of your enterprise <span>(100 words max)</span></h5>
                </div>
                <div class="enterprise-summary-field">
                    <textarea v-model="enterpriseSummary" cols="30" rows="8" maxlength="500" required></textarea>
                </div>
                <div class="enterprise-mission">
                    <h5 class="required no-margin">Mission</h5>
                </div>
                <div class="enterprise-mission-field">
                    <textarea v-model="enterpriseMission" maxlength="300" cols="50" rows="5" required></textarea>
                </div>
                <div class="enterprise-vision">
                    <h5 class="required no-margin">Vision</h5>
                </div>
                <div class="enterprise-vision-field">
                    <textarea v-model="enterpriseVision" maxlength="300" cols="50" rows="5" required></textarea>
                </div>
                <div class="enterprise-social-media">
                    <h5 class="no-margin">Enterprise Social Media Handle</h5>
                </div>
                <div class="enterprise-social-media-field">
                    <input type="url" v-model="enterpriseSocialMedia">
                </div>
                <div class="enterprise-website">
                    <h5 class="no-margin">Enterprise Website</h5>
                </div>
                <div class="enterprise-website-field">
                    <input type="url" v-model="enterpriseWebsite">
                </div>
            </div>

            <h5 class="required">Do you have a team of minimum two co-founders?</h5>
            <div class="box">
                <div class="option">
                    <input type="radio" id="team_yes" v-model="team" name="team" value="Team" required>
                    <label for="team_yes">Yes</label>
                </div>
                <div class="option">
                    <input type="radio" id="team_no" v-model="team" name="team" value="Self">
                    <label for="team_no">No</label>
                </div>
            </div>
            <p class='important-text'>**To ensure gender equality within our program, we appreciate applications that have at least one female co-founder.</p>
            <div class="cofounder-container">
                <div class="box-1">
                    <h5 class="required">Co-founder 1</h5>
                    <div class="co-founder">
                        <div class="co-founder__name">
                            <label for="co-founder_1">Name:</label>
                        </div>
                        <div class="co-founder__name-field">
                            <input type="text" id="co-founder_1" v-model="cofounderName1" required>
                        </div>
                        <div class="co-founder__gender">
                            <label>Gender:</label>
                        </div>
                        <div class="co-founder__gender-field">
                            <div class="gender-container">
                                <div class="option">
                                    <input type="radio" id="male1" v-model="gender1" name="gender1" value="Male" required>
                                    <label for="male1">Male</label>
                                </div>
                                <div class="option">
                                    <input type="radio" id="female1" v-model="gender1" name="gender1" value="Female">
                                    <label for="female1">Female</label>
                                </div>
                                <div class="option">
                                    <input type="radio" id="not-prefer1" v-model="gender1" name="gender1" value="Prefer not to say">
                                    <label for="not-prefer1">Prefer not to say</label>
                                </div>
                            </div>
                        </div>
                        <div class="co-founder__email">
                            <label for="email1">Email:</label>
                        </div>
                        <div class="co-founder__email-field">
                            <input type="email" v-model="email1" name="email1" id="email1" required>
                        </div>
                        <div class="co-founder__phone">
                            <label for="tel1">Phone:</label>
                        </div>
                        <div class="co-founder__phone-field">
                            <input type="tel" v-model="phone1" name="tel1" id="tel1" required>
                        </div>
                        <div class="co-founder__linkedin">
                            <label for="linkedin1">LinkedIn:</label>
                        </div>
                        <div class="co-founder__linkedin-field">
                            <input type="url" v-model="linkedin1" name="linkedin1" id="linkedin2" required>
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
                            <input type="text" id="co-founder_2" v-model="cofounderName2" required>
                        </div>
                        <div class="co-founder__gender">
                            <label>Gender:</label>
                        </div>
                        <div class="co-founder__gender-field">
                            <div class="gender-container">
                                <div class="option">
                                    <input type="radio" id="male2" v-model="gender2" name="gender2" value="Male" required>
                                    <label for="male2">Male</label>
                                </div>
                                <div class="option">
                                    <input type="radio" id="female2" v-model="gender2" name="gender2" value="Female">
                                    <label for="female2">Female</label>
                                </div>
                                <div class="option">
                                    <input type="radio" id="not-prefer2" v-model="gender2" name="gender2" value="Prefer not to say">
                                    <label for="not-prefer2">Prefer not to say</label>
                                </div>
                            </div>
                        </div>
                        <div class="co-founder__email">
                            <label for="email2">Email:</label>
                        </div>
                        <div class="co-founder__email-field">
                            <input type="email" v-model="email2" name="email2" id="email2" required>
                        </div>
                        <div class="co-founder__phone">
                            <label for="tel2">Phone:</label>
                        </div>
                        <div class="co-founder__phone-field">
                            <input type="tel" v-model="phone2" name="tel2" id="tel2" required>
                        </div>
                        <div class="co-founder__linkedin">
                            <label for="linkedin2">LinkedIn:</label>
                        </div>
                        <div class="co-founder__linkedin-field">
                            <input type="url" v-model="linkedin2" name="linkedin2" id="linkedin2" required>
                        </div>
                    </div>
                </div>

            </div>


            <h5 class="required">Does your enterprise work to reduce any of the following:</h5>
            <div class="checkbox-option">
                <input type="checkbox" name="reduce" id="carbon-emission" v-model="reduceProblem" value="Carbon emission">
                <label for="carbon-emission">Carbon emission</label>
            </div>
            <div class="checkbox-option">
                <input type="checkbox" name="reduce" id="unemployment" v-model="reduceProblem" value="Unemployment">
                <label for="unemployment">Unemployment</label>
            </div>
            <div class="checkbox-option">
                <input type="checkbox" name="reduce" id="poverty" v-model="reduceProblem" value="Poverty">
                <label for="poverty">Poverty</label>
            </div>
            <div class="checkbox-option">
                <input type="checkbox" name="reduce" id="none" v-model="reduceProblem" value="None of the above">
                <label for="none">None of the above</label>
            </div>
            
            <h5>If yes, how is your enterprise reducing carbon emission, creating jobs or fighting poverty? <span class="limit">(100 words max)</span></h5>
            <textarea name="reducing" v-model="howEnterpriseReduce" maxlength="500" cols="30" rows="8"></textarea>
        
            <h5 class="required">Do you know how to measure the impact of your work?</h5>
            <div class="box">
                <div class="option">
                    <input type="radio" id="measure_yes" v-model="impactMeasure" name="measure" value="1" required>
                    <label for="measure_yes">Yes</label>
                </div>
                <div class="option">
                    <input type="radio" id="measure_no" v-model="impactMeasure" name="measure" value="0">
                    <label for="measure_no">No</label>
                </div>
            </div>
            <h5>If yes, please tell us what methodology you use. <span class="limit">(100 words max)</span></h5>
            <textarea v-model="methodology" maxlength="500" cols="30" rows="8"></textarea>

            <h5 class="required">What innovation is your enterprise bringing to the local market? <span class="limit">(100 words max)</span></h5>
            <textarea v-model="enterpriseInnovation" maxlength="500" cols="30" rows="8" required></textarea>

            <h5 class="required">We respect and welcome both product and process innovation offered by enterprises and we would love to know more about your enterprise’s innovation. <span class="limit">(100 words max)</span></h5>
            <textarea v-model="enterpriseInnovationMore" maxlength="500" cols="30" rows="8" required></textarea>

            <h5 class="required">What is the stage of your venture?</h5>
            <div class="box">
                <div class="option">
                    <input type="radio" id="idea_stage" v-model="stage" name="stage" value="Idea Stage" required>
                    <label for="idea_stage">Idea Stage</label>
                </div>
                <div class="option">
                    <input type="radio" id="pilot_stage" v-model="stage" name="stage" value="Feasibility/Prototype/Pilot Stage">
                    <label for="pilot_stage">Feasibility/Prototype/Pilot Stage</label>
                </div>
                <div class="option">
                    <input type="radio" id="growth_stage" v-model="stage" name="stage" value="Growth Stage">
                    <label for="growth_stage">Growth Stage</label>
                </div>
            </div>

            <h5 class="required">Is the enterprise registered as an entity under the law of Bangladesh?</h5>
            <div class="box">
                <div class="option">
                    <input type="radio" id="registered_yes" v-model="registered" name="registered" value="1" required>
                    <label for="registered_yes">Yes</label>

                </div>
                <div class="option">
                    <input type="radio" id="registered_no" v-model="registered" name="registered" value="0">
                    <label for="registered_no">No</label>
                </div>
            </div>
            <h5 class="mt">If yes, what is the legal status of your venture?</h5>
            <div class="box">
                <div class="option">
                    <input type="radio" id="limited-company" v-model="legalStatus" name="legalStatus" value="For profit/Limited company" required>
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
                <input type="text" id="other" v-model="legalStatus">
            </div>

            <h5 class="required">How does your enterprise make money? <span class="limit">(100 words max)</span></h5>
            <textarea v-model="enterpriseMakeMoney" maxlength="500" cols="30" rows="8" required></textarea>

            <h5 class="required">How much revenue do you have at the moment (in BDT)?</h5>
            <div class="option">
                <input type="radio" id="revenue-a" v-model="revenue" name="revenue" value="0 - 100000" required>
                <label for="revenue-a">0 - 100000</label>
            </div>
            <div class="option">
                <input type="radio" id="revenue-b" v-model="revenue" name="revenue" value="100000 - 500000">
                <label for="revenue-b">100000 - 500000</label>
            </div>
            <div class="option">
                <input type="radio" id="revenue-c" v-model="revenue" name="revenue" value="500000 - 2000000">
                <label for="revenue-c">500000 - 2000000</label>
            </div>
            <div class="option">
                <input type="radio" id="revenue-d" v-model="revenue" name="revenue" value="2000000 - 5000000">
                <label for="revenue-d">2000000 - 5000000</label>
            </div>
            <div class="option">
                <input type="radio" id="revenue-e" v-model="revenue" name="revenue" value="> 5000000">
                <label for="revenue-e">> 5000000</label>
            </div>

            <h5 class="required">How many customers are you serving right now?</h5>
            <div class="option">
                <input type="radio" id="customers-a" v-model="customers" name="customers" value="0 - 100" required>
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

            <h5 class="required">Please share any media link where your enterprise has been featured</h5>
            <div class="media-link-group">
                <input type="url" v-model="media_link_1" name="media-link" placeholder="link 1" class="mb" required>
                <input type="url" v-model="media_link_2" name="media-link" placeholder="link 2" class="mb">
                <input type="url" v-model="media_link_3" name="media-link" placeholder="link 3" class="mb">
                <input type="url" v-model="media_link_4" name="media-link" placeholder="link 4" class="mb">
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
                <input type="file" @change='handleFileUpload' name="pitch_deck" required>

                <input type="submit">
            </div>

            <p v-if="this.show_message">Thank you for applying to YY Goshthi Spring 2022 Cohort. We will get back to you once the application closes.</p>
        </form>
    </div>
</template>

<script>
    // import { post } from '@/assets/scripts/api';
    import axios from 'axios'

    export default {
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
                enterpriseMakeMoney: '',
                revenue: '',
                customers: '',
                media_link_1: '',
                media_link_2: '',
                media_link_3: '',
                media_link_4: '',
                year: '',
                season: 'Spring',
                files: '',
                show_message: false,
            }
        },
   
        methods: {        
            submit: async function () {
                const data = new FormData();
                data.set('name_of_business',this.enterpriseName);
                data.set('summery_of_experience',this.enterpriseSummary);
                data.set('mission',this.enterpriseMission);
                data.set('vision',this.enterpriseVision);
                data.set('enterprise_social_media',this.enterpriseSocialMedia);
                data.set('enterprise_website',this.enterpriseWebsite);
                data.set('founder_type',this.team);
                data.set('co_founder_name_one',this.cofounderName1);
                data.set('co_founder_gender_one',this.gender1);
                data.set('co_founder_email_one',this.email1);
                data.set('co_founder_mobile_one',this.phone1);
                data.set('co_founder_linkedin_one',this.linkedin1);
                data.set('co_founder_name_two',this.cofounderName2);
                data.set('co_founder_gender_two',this.gender2);
                data.set('co_founder_email_two',this.email2);
                data.set('co_founder_mobile_two',this.phone2);
                data.set('co_founder_linkedin_two',this.linkedin2);
                data.set('reduce_problem',this.reduceProblem.toString());
                data.set('reduce_problem_process',this.howEnterpriseReduce);
                data.set('is_known_impact_of_work',this.impactMeasure);
                data.set('methodology_of_work',this.methodology);
                data.set('innovation',this.enterpriseInnovation);
                data.set('experience_of_innovation',this.enterpriseInnovationMore);
                data.set('stage_of_ventures',this.stage);
                data.set('is_registered_under_law',this.registered);
                data.set('legal_status_ventures',this.legalStatus);
                data.set('current_revenue_range',this.revenue);
                data.set('customer_range',this.customers);
                data.set('media_links',[this.media_link_1, this.media_link_2, this.media_link_3, this.media_link_4]);
                data.set('year',this.year);
                data.set('season',this.season);
                data.set('pitch_deck', this.files);
            
                axios.post('https://yyv.yyventures.org/api/yyg-application-submit-form/create', data)
                .then(response => {
                    if (response.status == 200) {
                    this.show_message = true
                    }
                })
                .catch(error => {
                    console.log(error)
                })},
                    
                getCurrentyear: function(){
                    const date = new Date();
                    const year = date.getFullYear();
                    this.year = year;
                },
                handleFileUpload: function(e){
                    this.files = e.target.files[0];
                },
            }
        
        }

</script>

<style lang="scss" scoped>
    #application{
        padding: 10rem 10rem;

        @media screen and (max-width: 600px){
            padding: 8rem 0;
        }

        .heading-container{
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 80px;
            .img-container{
                height: 100px;
                img{
                    height: 100%;
                    object-fit: contain;
                }
            }
            .heading{
                span{
                    display: block;
                    font-size: 30px;
                    height: 35px;

                }
                .season{
                    color: #1e87f0;
                    font-weight: 700;
                }
                .date{
                    color: #3A3A3A;
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

            .enterprise-info-container{
                display: grid;
                grid-template-columns: [type-start] 20% [type-end field-stat] 80% [field-end];
                grid-template-rows: repeat(6, [row-start] min-content [row-end]);
                grid-gap: 10px 20px;

                span{
                    display: block;
                    font-weight: 300;
                }
            }

            .cofounder-container{

                display: grid;
                grid-template-columns: repeat(2, 1fr);
                grid-gap: 40px;

                .box-1{
                }
                .box-2{
                }
            }

            .box{
                display: flex;
                gap: 20px;
            }
            .sm-box{
                width: 70%;
            }
            .component{
                display: flex;
                gap: 50px;
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
                align-items: center;
            }
            // .label-container{
            //     display: flex;
            //     flex-direction: column;
            //     justify-content: space-between;
            //     align-items: flex-end;
            // }
            // .input-container{
            //     display: flex;
            //     flex-direction: column;
            //     gap: 10px;
                // background-color: #c7265b;

                .gender-container{
                    display: flex;
                    gap: 10px;
                }

            // }

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
                .btn-remove{
                    background-color: rgba(255, 0, 0, 0.781);
                }
                .btn-add{
                    background-color: rgba(0, 128, 0, 0.781);

                }
            }
            .mb{
                margin-bottom: 10px;
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
                // border-bottom: 1px solid #3A3B3A;
                padding: 7px;
                // font-size: 30px;

                &:focus{
                    outline: none;
                    border-bottom: 2px solid #3A3B3A;
                }
            }
            input[type='text'],
            input[type='url'],
            textarea{
                font-size: 16px;
                width: 100%;
                border: none;
                padding: 7px;
            }

            input[type='radio']{
                margin: 0 3px;
            }

            input[type='file']{
                padding: 10px 20px;
                background-color: white;
                width: 100%;
                margin-bottom: 25px;
                cursor: pointer;
            }

            input[type='submit']{
                display: block;
                width: 100%;
                font-size: 20px;
                font-weight: 700;
                color: white;
                background: #1e87f0;
                border: none;
                padding: 10px 20px;
                &:hover{
                    filter: brightness(90%);
                    cursor: pointer;
                }
            }

            .important-text{
                font-style: italic;
                color: #1e87f0;
            }
        }

    }
</style>