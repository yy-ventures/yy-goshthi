<template>
    <div id="application">
        <h1 class="heading">YY Goshthi Spring {{getCurrentyear()}} Application</h1>
        <form @submit.prevent="submit()">
            <h5>Name of your enterprise</h5>
            <input type="text" v-model="enterpriseName" required>

            <h5>Summary of your enterprise (100 words max)</h5>
            <textarea v-model="enterpriseSummary" cols="30" rows="10" maxlength="500" required></textarea>

            <h5>Mission</h5>
            <textarea v-model="enterpriseMission" maxlength="300" cols="50" rows="5" required></textarea>

            <h5>Vision</h5>
            <textarea v-model="enterpriseVision" maxlength="300" cols="50" rows="5" required></textarea>

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
            <p class='important-text'>**To ensure gender equality within our program, we appreciate applications that have at least one female co-founder.</p>

            <h5>Co-founder 1</h5>
            <div class="co-founder">
                <div class="option label-container">
                    <label for="co-founder_1">Name:</label>
                    <label>Gender:</label>
                    <label for="email1">Email:</label>
                    <label for="tel1">Phone:</label>
                    <label for="linkedin1">LinkedIn:</label>
                </div>
                <div class="option input-container">
                    <input type="text" id="co-founder_1" v-model="cofounderName1" required>
                    <div class="gender-container">
                        <input type="radio" id="male1" v-model="gender1" name="gender1" value="Male" required>
                        <label for="male1">Male</label>
                        <input type="radio" id="female1" v-model="gender1" name="gender1" value="Female">
                        <label for="female1">Female</label>
                        <input type="radio" id="not-prefer1" v-model="gender1" name="gender1" value="Prefer not to say">
                        <label for="not-prefer1">Prefer not to say</label>
                    </div>
                    <input type="email" v-model="email1" name="email1" id="email1" required>
                    <input type="tel" v-model="phone1" name="tel1" id="tel1" required>
                    <input type="url" v-model="linkedin1" name="linkedin1" id="linkedin2" required>
                </div>
            </div>

            <h5>Co-founder 2</h5>
            <div class="co-founder">
                <div class="option label-container">
                    <label for="co-founder_2">Name:</label>
                    <label>Gender:</label>
                    <label for="email2">Email:</label>
                    <label for="tel2">Phone:</label>
                    <label for="linkedin2">LinkedIn:</label>
                </div>
                <div class="option input-container">
                    <input type="text" id="co-founder_2" v-model="cofounderName2" required>
                    <div class="gender-container">
                        <input type="radio" id="male2" v-model="gender2" name="gender2" value="Male" required>
                        <label for="male2">Male</label>
                        <input type="radio" id="female2" v-model="gender2" name="gender2" value="Female">
                        <label for="female2">Female</label>
                        <input type="radio" id="not-prefer2" v-model="gender2" name="gender2" value="Prefer not to say">
                        <label for="not-prefer2">Prefer not to say</label>
                    </div>
                    <input type="email" v-model="email2" name="email2" id="email2" required>
                    <input type="tel" v-model="phone2" name="tel2" id="tel2" required>
                    <input type="url" v-model="linkedin2" name="linkedin2" id="linkedin2" required>
                </div>
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
                <input type="text" id="other" v-model="otherLegalStatus">
            </div>

            <h5>How does your enterprise make money? (100 words max)</h5>
            <textarea v-model="enterpriseMakeMoney" maxlength="500" cols="30" rows="10" required></textarea>

            <h5>How much revenue do you have at the moment (in BDT)?</h5>
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

            <h5>How many customers are you serving right now?</h5>
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

            <h5>Please share any media link where your enterprise has been featured</h5>
            <input type="url" v-model="mediaLink">

            <h5>Please upload your pitch deck</h5>
            <p class='important-text'>**Your pitch deck will be provided with your full application to the panel of judges. Please make sure your pitch deck has the following components:</p>
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
                    name_of_business: this.enterpriseName,
                    summery_of_experience: this.enterpriseSummary,
                    mission: this.enterpriseMission,
                    vision: this.enterpriseVision,
                    enterprise_social_media: this.enterpriseSocialMedia,
                    enterprise_website: this.enterpriseWebsite,
                    founder_type: this.team,
                    co_founder_name_one: this.cofounderName1,
                    co_founder_gender_one: this.gender1,
                    co_founder_email_one: this.email1,
                    co_founder_mobile_one: this.phone1,
                    co_founder_linkedin_one: this.linkedin1,
                    co_founder_name_two: this.cofounderName2,
                    co_founder_gender_two: this.gender2,
                    co_founder_email_two: this.email2,
                    co_founder_mobile_two: this.phone2,
                    co_founder_linkedin_two: this.linkedin2,
                    reduce_problem: this.reduce.toString(),
                    reduce_problem_process: this.howEnterpriseReduce,
                    is_known_impact_of_work : this.impactMeasure,
                    methodology_of_work: this.methodology,
                    innovation: this.enterpriseInnovation,
                    experience_of_innovation: this.enterpriseInnovationMore,
                    stage_of_ventures: this.stage,
                    is_registered_under_law: this.registered,
                    legal_status_ventures: this.legalStatus,
                    make_money_plan: this.enterpriseMakeMoney,
                    current_revenue_range: this.revenue,
                    customer_range: this.customers,
                    media_links: this.mediaLink,
                    year: '2022',
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
                window.location.href = 'https://incubator.yy.ventures/';
            }, 3000);
            },
            getCurrentyear: function(){
                const date = new Date();
                const year = date.getFullYear();

                return year;
            }
        },
        data: () => ({

            name_of_business: '',
            summery_of_experience: '',
            mission: '',
            vision: '',
            enterprise_social_media: '',
            enterprise_website: '',
            founder_type: '',
            co_founder_name_one: '',
            co_founder_gender_one: '',
            co_founder_email_one: '',
            co_founder_mobile_one: '',
            co_founder_linkedin_one: '',
            co_founder_name_two: '',
            co_founder_gender_two: '',
            co_founder_email_two: '',
            co_founder_mobile_two: '',
            co_founder_linkedin_two: '',
            reduce_problem: [],
            reduce_problem_process: '',
            is_known_impact_of_work : '',
            methodology_of_work: '',
            innovation: '',
            experience_of_innovation: '',
            stage_of_ventures: '',
            is_registered_under_law: '',
            legal_status_ventures: '',
            make_money_plan: '',
            current_revenue_range: '',
            customer_range: '',
            media_links: '',
            year: '',
            show_message: false,
        }),
    }

</script>

<style lang="scss" scoped>
    #application{
        padding: 10rem 15rem;

        @media screen and (max-width: 600px){
            padding: 8rem 0;
        }

        .heading{
            text-align: center;
            margin-bottom: 5rem;
        }

        form{
            // border: 1px solid black;
            padding: 50px 70px;
            background-color: #eee;

            @media screen and (max-width: 600px){
                padding: 50px 40px;
            }

            h5{
                font-size: 20px;
                font-weight: 700;
                margin-bottom: 5px;

            }
            
            .co-founder{
                display: flex;
                gap: 10px;
            }
            .label-container{
                display: flex;
                flex-direction: column;
                justify-content: space-between;
                align-items: flex-end;
                // background-color: #1e87f0;
            }
            .input-container{
                display: flex;
                flex-direction: column;
                gap: 10px;
                // background-color: #c7265b;

            }
            .gender-container{
                margin: 5px 0;
            }
            .mb{
                margin-top: 10px;                
            }
            .h-align{
                display: flex;
                gap: 20px;
            }

            .option{
                margin-bottom: 10px;
            }
    
            input[type='text'],
            input[type='url'],
            input[type='tel'],
            input[type='email']
            {
                height: 30px;
                border: none;
                // border-bottom: 1px solid #3A3B3A;
                padding: 7px;
                font-size: 16px;

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
                border: 1px solid grey;
                width: 100%;
                border-radius: 5px;
                margin-bottom: 25px;
                cursor: pointer;
            }

            input[type='submit']{
                display: block;
                width: 100%;
                border-radius: 5px;
                font-size: 20px;
                font-weight: 700;
                color: white;
                background: #c7265b;
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