<template>
    <div id="application">
        <h1 class="heading">YY Goshthi Spring 2022 Application</h1>
        <form>
            <h5>Name of your enterprise</h5>
            <input type="text" v-model="enterpriseName" required>

            <h5>Summary of your enterprise (100 words max)</h5>
            <textarea v-model="enterpriseSummary" cols="50" rows="5" required></textarea>

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
            <h5 class="mb">If yes, please tell us what methodology you use. (100 words max)</h5>
            <textarea v-model="methodology" cols="30" rows="10"></textarea>

            <h5>What innovation is your enterprise bringing to the local market? (100 words max)</h5>
            <textarea v-model="enterpriseInnovation" cols="30" rows="10" required></textarea>

            <h5>We respect and welcome both product and process innovation offered by enterprises and we would love to know more about your enterprise’s innovation. (100 words max)</h5>
            <textarea v-model="enterpriseInnovationMore" cols="30" rows="10" required></textarea>

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
            <textarea v-model="enterpriseMakeMoney" cols="30" rows="10" required></textarea>

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
        </form>
    </div>
</template>

<script>

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