<template>
  <div id="home-page">
    <!-- <dark-nav></dark-nav> -->
    <!-- <programs-nav></programs-nav> -->
    <div id="home"></div>
    <home-hero></home-hero>
    <!-- <Incubation></Incubation> -->
    <div id="about"></div>
    <incubator-text></incubator-text>
    <!-- <Program :data="incubator_program"></Program> -->
    <div id="impact"></div>
    <!-- <programs-impact class="faded_out"></programs-impact> -->
    <OurImpact class="faded_out"></OurImpact>
    <!-- <Related class="faded_out"></Related> -->
    <div id="benefits"></div>
    <HowWeHelp></HowWeHelp>
    <!-- <picture-grid :data="incubator_benefits"></picture-grid> -->
    <!-- <Conditions></Conditions> -->
    <div id="eligibility"></div>
    <EligibilityNew class="faded_out"></EligibilityNew>
    <!-- <Eligibility :data="incubator_eligibility" class="faded_out"></Eligibility> -->
    <!-- <programs-portfolio></programs-portfolio> -->
    <div id="alumni"></div>
    <NotableAlumni></NotableAlumni>
    <!-- <Carousel></Carousel> -->
    <!-- <Cta></Cta> -->
    <Video></Video>
    <div id="experts"></div>
    <ExpertsFacilitators></ExpertsFacilitators>

    <ProgramsTeam></ProgramsTeam>

    <div id="apply"></div>
    <Join></Join>
    <!-- <call-to-action :data="incubator_call_to_action"></call-to-action>
    <incubator-partners></incubator-partners> -->
    <!-- <Partner></Partner> -->
    <!-- <about-footer></about-footer> -->
  </div>
</template>

<script>
import DarkNav from '~/components/DarkNav';
import Hero from '~/components/yy_goshti/Hero';
import Incubation from '~/components/yy_goshti/Incubation';
import Conditions from '~/components/yy_goshti/Conditions';
import Cta from '~/components/yy_goshti/Cta';
import Carousel from '~/components/Carousel';
import HomeHero from '~/components/home-redo/HomeHero';
import IncubatorText from '~/components/IncubatorText';

import Program from '~/components/Program';
// import Partner from '~/components/Partner';
import CallToAction from '~/components/CallToAction';

import PortfolioInvestments from '~/components/portfolio-redo/PortfolioInvestments';
import PortfolioContact from '~/components/portfolio-redo/PortfolioContact';

import HomeText from '~/components/home-redo/HomeText';
import HomePortfolio from '~/components/home-redo/HomePortfolio';
import HomeCta from '~/components/home-redo/HomeCta';
// import AboutFooter from '~/components/about-redo/AboutFooter';

import ProgramsImpact from '~/components/ProgramsImpact';
import ProgramsConditions from '~/components/ProgramsConditions';
import ProgramsCta from '~/components/ProgramsCta';
import ProgramsServices from '~/components/ProgramsServices';
import ProgramsIncubation from '~/components/ProgramsIncubation';
import ProgramsPortfolio from '~/components/ProgramsPortfolio';
import ProgramsNav from '~/components/ProgramsNav';

import IncubatorPartners from '~/components/IncubatorPartners';
import Eligibility from '~/components/washic/Eligibility';
import PictureGrid from '~/components/PictureGrid';

// import incubator_partners from '~/assets/data/incubator_partners.json';
import incubator_call_to_action from '~/assets/data/incubator_call_to_action.json';
import incubator_eligibility from '~/assets/data/incubator_eligibility.json';
import incubator_program from '~/assets/data/incubator_program.json';
import incubator_benefits from '~/assets/data/incubator_benefits.json';
import wash_benefits from '~/assets/data/wash_benefits.json';

// LANDING PAGE NEW (NINAD)
import OurImpact from '~/components/landing-page-new/OurImpact.vue';
import Related from '~/components/landing-page-new/Related.vue';
import HowWeHelp from '~/components/landing-page-new/HowWeHelp.vue';
import EligibilityNew from '~/components/landing-page-new/Eligibility.vue';
import NotableAlumni from '~/components/landing-page-new/NotableAlumni.vue';
import Video from '~/components/landing-page-new/Video.vue';
import Join from '~/components/landing-page-new/Join.vue';
import ExpertsFacilitators from '~/components/landing-page-new/ExpertsFacilitators.vue';
import ProgramsTeam from '~/components/landing-page-new/ProgramsTeam.vue';

import {
  toggle_class_on_focus,
  typewriter,
  dom,
  run_function_on_focus,
  add_class_on_focus,
} from '@/assets/scripts/dom_utils';

export default {
  components: {
    PortfolioInvestments,
    PortfolioContact,
    Hero,
    Incubation,
    Conditions,
    Cta,
    IncubatorPartners,
    Program,
    CallToAction,
    Eligibility,
    Carousel,
    PictureGrid,
    IncubatorText,

    DarkNav,
    HomeText,
    HomePortfolio,
    HomeCta,
    HomeHero,
    // Partner,
    // AboutFooter,

    ProgramsImpact,
    ProgramsConditions,
    ProgramsCta,
    ProgramsServices,
    ProgramsIncubation,
    ProgramsPortfolio,
    ProgramsNav,

    // LANDING PAGE NEW (NINAD)
    OurImpact,
    Related,
    HowWeHelp,
    EligibilityNew,
    NotableAlumni,
    Video,
    ExpertsFacilitators,
    ProgramsTeam,
    Join
  },

  data: () => ({
    incubator_eligibility,
    incubator_call_to_action,
    incubator_program,
    incubator_benefits,
    wash_benefits,
    // incubator_partners,
  }),

  mounted: () => {
    toggle_class_on_focus({
      ['.highlight']: 'scale',
    });

    typewriter(
      ['Incubating Change', 'Building Social Businesses', 'Improving Lives'],
      100,
      1000
    )(dom('.write'));

    add_class_on_focus({
      ['.faded_out']: 'fade_in',
      ['#program #top_section']: 'scale_down',
      ['#startups']: 'count_startups',
      ['#lives']: 'count_lives',
      ['#programs']: 'count_programs',
    });
  },
};
</script>

<style lang="less">
#program #top_section #texts .p {
  font-size: clamp(18px, 2vw, 21px);
}

#condition_1 {
  background: blue;
}
#condition_2 {
  background: yellow;
}
</style>
