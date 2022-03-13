<template>
    <div id="application">
        <h1 class="heading">YY Goshthi Spring {{getCurrentyear()}} Application</h1>
        <form @submit.prevent="submit()">
            <h5>Name of your enterprise</h5>
            <input type="text" v-model="enterpriseName" required>

            <h5>Summary of your enterprise (100 words max)</h5>
            <textarea v-model="enterpriseSummary" cols="50" rows="5" maxlength="500" required></textarea>

            <h5>Mission</h5>
            <textarea v-model="enterpriseMission" cols="50" rows="5" required></textarea>

            <h5>Vision</h5>
            <textarea v-model="enterpriseVision" cols="50" rows="5" required></textarea>

            <h5>Enterprise Social Media Handle</h5>
            <input type="url" v-model="enterpriseSocialMedia">

            <h5>Enterprise Website</h5>
            <input type="url" v-model="enterpriseWebsite">

            <h5>Do you have a team of minimum two co-founders?</h5>
            <div class="option">
                <input type="radio" id="team_yes" v-model="team" name="team" value="Yes" required>
                <label for="team_yes">Yes</label>
            </div>
            <div class="option">
                <input type="radio" id="team_no" v-model="team" name="team" value="No">
                <label for="team_no">No</label>
            </div>
            <p>**To ensure gender equality within our program, we appreciate applications that have at least one female co-founder.</p>

            <h5>Co-founder 1</h5>
            <div class="option h-align">
                <label for="co-founder_1">Name:</label>
                <input type="text" id="co-founder_1" v-model="cofounderName1" required>
            </div>
            <div class="option">
                <label>Gender:</label>
                <input type="radio" id="male1" v-model="gender1" name="gender1" value="Male" required>
                <label for="male1">Male</label>
                <input type="radio" id="female1" v-model="gender1" name="gender1" value="Female">
                <label for="female1">Female</label>
                <input type="radio" id="not-prefer1" v-model="gender1" name="gender1" value="Prefer not to say">
                <label for="not-prefer1">Prefer not to say</label>
            </div>
            <div class="option">
                <label for="email1">Email:</label>
                <input type="email" v-model="email1" name="email1" id="email1" required>
            </div>
            <div class="option">
                <label for="tel1">Phone:</label>
                <input type="tel" v-model="phone1" name="tel1" id="tel1" required>
            </div>
            <div class="option h-align">
                <label for="linkedin1">LinkedIn:</label>
                <input type="url" v-model="linkedin1" name="linkedin1" id="linkedin1" required>
            </div>

            <h5>Co-founder 2</h5>
            <div class="option h-align">
                <label for="co-founder_2">Name:</label>
                <input type="text" id="co-founder_2" v-model="cofounderName2" required>
            </div>
            <div class="option">
                <label>Gender:</label>
                <input type="radio" id="male2" v-model="gender2" name="gender2" value="Male" required>
                <label for="male2">Male</label>
                <input type="radio" id="female2" v-model="gender2" name="gender2" value="Female">
                <label for="female2">Female</label>
                <input type="radio" id="not-prefer2" v-model="gender2" name="gender2" value="Prefer not to say">
                <label for="not-prefer2">Prefer not to say</label>
            </div>
            <div class="option">
                <label for="email2">Email:</label>
                <input type="email" v-model="email2" name="email2" id="email2" required>
            </div>
            <div class="option">
                <label for="tel2">Phone:</label>
                <input type="tel" v-model="phone2" name="tel2" id="tel2" required>
            </div>
            <div class="option h-align">
                <label for="linkedin2">LinkedIn:</label>
                <input type="url" v-model="linkedin2" name="linkedin2" id="linkedin2" required>
            </div>

            <h5>Does your enterprise work to reduce any of the following:</h5>
            <div class="option">
                <input type="checkbox" name="reduce" id="carbon-emission" v-model="reduce" value="Carbon emission">
                <label for="carbon-emission">Carbon emission</label>
            </div>
            <div class="option">
                <input type="checkbox" name="reduce" id="unemployment" v-model="reduce" value="Unemployment">
                <label for="unemployment">Unemployment</label>
            </div>
            <div class="option">
                <input type="checkbox" name="reduce" id="poverty" v-model="reduce" value="Poverty">
                <label for="poverty">Poverty</label>
            </div>
            <div class="option">
                <input type="checkbox" name="reduce" id="none" v-model="reduce" value="None of the above">
                <label for="none">None of the above</label>
            </div>
            <h5>If yes, how is your enterprise reducing carbon emission, creating jobs or fighting poverty? (100 words max)</h5>
            <textarea name="reducing" v-model="howEnterpriseReduce" maxlength="500" cols="30" rows="10"></textarea>
        
            <h5>Do you know how to measure the impact of your work?</h5>
            <div class="option">
                <input type="radio" id="measure_yes" v-model="impactMeasure" name="measure" value="Yes" required>
                <label for="measure_yes">Yes</label>
            </div>
            <div class="option">
                <input type="radio" id="measure_no" v-model="impactMeasure" name="measure" value="No">
                <label for="measure_no">No</label>
            </div>
            <h5 class="mb">If yes, please tell us what methodology you use. (100 words max)</h5>
            <textarea v-model="methodology" maxlength="500" cols="30" rows="10"></textarea>

            <h5>What innovation is your enterprise bringing to the local market? (100 words max)</h5>
            <textarea v-model="enterpriseInnovation" maxlength="500" cols="30" rows="10" required></textarea>

            <h5>We respect and welcome both product and process innovation offered by enterprises and we would love to know more about your enterprise’s innovation. (100 words max)</h5>
            <textarea v-model="enterpriseInnovationMore" maxlength="500" cols="30" rows="10" required></textarea>

            <h5>What is the stage of your venture?</h5>
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

            <h5>Is the enterprise registered as an entity under the law of Bangladesh?</h5>
            <div class="option">
                <input type="radio" id="registered_yes" v-model="registered" name="registered" value="Yes" required>
                <label for="registered_yes">Yes</label>

            </div>
            <div class="option">
                <input type="radio" id="registered_no" v-model="registered" name="registered" value="No">
                <label for="registered_no">No</label>
            </div>
            <h5 class="mb">If yes, what is the legal status of your venture?</h5>
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
            <div class="option h-align">
                <label for="other">Other: </label>
                <input type="text" id="other" v-model="legalStatus">
            </div>

            <h5>How does your enterprise make money? (100 words max)</h5>
            <textarea v-model="enterpriseMakeMoney" maxlength="500" cols="30" rows="10" required></textarea>

            <h5>How much revenue do you have at the moment (in BDT)?</h5>
            <div class="option">
                <input type="radio" id="revenue-a" v-model="revenue" name="revenue" value="Idea Stage" required>
                <label for="revenue-a">0 - 100000</label>
            </div>
            <div class="option">
                <input type="radio" id="revenue-b" v-model="revenue" name="revenue" value="Feasibility/Prototype/Pilot Stage">
                <label for="revenue-b">100000 - 500000</label>
            </div>
            <div class="option">
                <input type="radio" id="revenue-c" v-model="revenue" name="revenue" value="Growth Stage">
                <label for="revenue-c">500000 - 2000000</label>
            </div>
            <div class="option">
                <input type="radio" id="revenue-d" v-model="revenue" name="revenue" value="Growth Stage">
                <label for="revenue-d">2000000 - 5000000</label>
            </div>
            <div class="option">
                <input type="radio" id="revenue-e" v-model="revenue" name="revenue" value="Growth Stage">
                <label for="revenue-e">> 5000000</label>
            </div>

            <h5>How many customers are you serving right now?</h5>
            <div class="option">
                <input type="radio" id="customers-a" v-model="customers" name="customers" value="Idea Stage" required>
                <label for="customers-a">0 - 100</label>
            </div>
            <div class="option">
                <input type="radio" id="customers-b" v-model="customers" name="customers" value="Feasibility/Prototype/Pilot Stage">
                <label for="customers-b">100 - 1000</label>
            </div>
            <div class="option">
                <input type="radio" id="customers-c" v-model="customers" name="customers" value="Growth Stage">
                <label for="customers-c">1000 - 10000</label>
            </div>
            <div class="option">
                <input type="radio" id="customers-d" v-model="customers" name="customers" value="Growth Stage">
                <label for="customers-d">> 10000</label>
            </div>

            <h5>Please share any media link where your enterprise has been featured</h5>
            <input type="url" v-model="mediaLink">

            <h5>Please upload your pitch deck</h5>
            <p>**Your pitch deck will be provided with your full application to the panel of judges. Please make sure your pitch deck has the following components:</p>
            <ul>
                <li>Problem</li>
                <li>Market Opportunity</li>
                <li>Solution</li>
                <li>Product/Service</li>
                <li>Business Model</li>
                <li>Revenue Structure</li>
                <li>Traction</li>
                <li>Roadmap</li>
                <li>Call to Action</li>
                <li>Team</li>
            </ul>
            <input type="file">

            <input type="submit">

            <p v-if="this.show_message">Thank you for applying to YY Goshthi Spring 2022 Cohort. We will get back to you once the application closes.</p>
        </form>
    </div>
</template>

<script>
    import { post } from '@/assets/scripts/api';

    export default {
        methods: {
            submit: async function () {
            this.show_message = true;
            const body = {
                records: [
                {
                    fields: {
                    enterpriseName: this.enterpriseName,
                    enterpriseSummary: this.enterpriseSummary,
                    enterpriseMission: this.enterpriseMission,
                    enterpriseVision: this.enterpriseVision,
                    enterpriseSocialMedia: this.enterpriseSocialMedia,
                    enterpriseWebsite: this.enterpriseWebsite,
                    team: this.team,
                    cofounderName1: this.cofounderName1,
                    gender1: this.gender1,
                    email1: this.email1,
                    phone1: this.phone1,
                    linkedin1: this.linkedin1,
                    cofounderName2: this.cofounderName2,
                    gender2: this.gender2,
                    email2: this.email2,
                    phone2: this.phone2,
                    linkedin2: this.linkedin2,
                    reduce: this.reduce.toString(),
                    howEnterpriseReduce: this.howEnterpriseReduce,
                    impactMeasure : this.impactMeasure,
                    methodology: this.methodology,
                    enterpriseInnovation: this.enterpriseInnovation,
                    enterpriseInnovationMore: this.enterpriseInnovationMore,
                    stage: this.stage,
                    registered: this.registered,
                    legalStatus: this.legalStatus,
                    enterpriseMakeMoney: this.enterpriseMakeMoney,
                    revenue: this.revenue,
                    customers: this.customers,
                    mediaLink: this.mediaLink,
                    year: getCurrentyear(),
                    },
                },
                ],
            };
            console.log(body.records);
            const result = await post(
                'http://yyv.yyventures.org/api/yyg-application-submit-form/create',
                body
            );
            console.log(result);
            setTimeout(() => {
                window.location.href = 'https://yy.ventures';
            }, 3000);
            },
            getCurrentyear: function(){
                const date = new Date();
                const year = date.getFullYear();

                return year;
            }
        },
        data: () => ({
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
            reduce: [],
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
            mediaLink: '',
            show_message: false,
        }),
    }

</script>

<style lang="scss" scoped>
    #application{
        padding: 10rem 8rem;

        .heading{
            text-align: center;
        }

        form{
            // border: 1px solid black;
            padding: 30px 50px;
            background-color: #eee;

            h5{
                font-size: 20px;
                font-weight: 700;
                margin-bottom: 5px;

            }
            .mb{
                margin-top: 10px;                
            }
            .h-align{
                display: flex;
                gap: 20px;
            }
    
            input[type='text'],
            input[type='url']{
                height: 30px;
                border: none;
                // border-bottom: 1px solid #3A3B3A;
                font-size: 16px;

                &:focus{
                    outline: none;
                    border-bottom: 2px solid #3A3B3A;
                }
            }
            input[type='text'],
            input[type='url'],
            textarea{
                width: 100%;
                border: none;
            }
        }

    }
</style>