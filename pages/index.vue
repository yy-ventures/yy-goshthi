<template>
  <div id="home-page">
    <!-- Home hero section -->
    <div id="home"></div>
    <home-hero></home-hero>
    <!-- About section -->
    <div id="about"></div>
    <incubator-text></incubator-text>
    <!-- Impact section -->
    <div id="impact"></div>
    <OurImpact class="faded_out"></OurImpact>
    <!-- How we help section -->
    <div id="benefits"></div>
    <HowWeHelp></HowWeHelp>
    <!-- eligibility section -->
    <div id="eligibility"></div>
    <EligibilityNew class="faded_out"></EligibilityNew>
    <!-- Notable alumni section-->
    <div id="alumni"></div>
    <NotableAlumni></NotableAlumni>
    <!-- Video section -->
    <Video></Video>
    <!-- Experts & facilitators section -->
    <div id="experts"></div>
    <ExpertsFacilitators></ExpertsFacilitators>
    <!-- Programs team section -->
    <ProgramsTeam></ProgramsTeam>
    <!-- Join  sections -->
    <div id="apply"></div>
    <Join></Join>
  </div>
</template>

<script>
import HomeHero from "~/components/home-page/HomeHero";
import IncubatorText from "~/components/home-page/IncubatorText.vue";
import OurImpact from "~/components/home-page/OurImpact.vue";
import Related from "~/components/home-page/Related.vue";
import HowWeHelp from "~/components/home-page/HowWeHelp.vue";
import EligibilityNew from "~/components/home-page/Eligibility.vue";
import NotableAlumni from "~/components/home-page/NotableAlumni.vue";
import Video from "~/components/home-page/Video.vue";
import Join from "~/components/home-page/Join.vue";
import ExpertsFacilitators from "~/components/home-page/ExpertsFacilitators.vue";
import ProgramsTeam from "~/components/home-page/ProgramsTeam.vue";

import {
  toggle_class_on_focus,
  typewriter,
  dom,
  run_function_on_focus,
  add_class_on_focus,
} from "@/assets/scripts/dom_utils";

export default {
  components: {
    HomeHero,
    IncubatorText,
    OurImpact,
    Related,
    HowWeHelp,
    EligibilityNew,
    NotableAlumni,
    Video,
    ExpertsFacilitators,
    ProgramsTeam,
    Join,
  },

  mounted: () => {
    toggle_class_on_focus({
      [".highlight"]: "scale",
    });

    typewriter(
      ["Incubating Change", "Building Social Businesses", "Improving Lives"],
      100,
      1000
    )(dom(".write"));

    add_class_on_focus({
      [".faded_out"]: "fade_in",
      ["#program #top_section"]: "scale_down",
      ["#startups"]: "count_startups",
      ["#lives"]: "count_lives",
      ["#programs"]: "count_programs",
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
