<template lang="pug">
main
  Navigation
  nuxt
  FooterNew
  //- Footer
</template>

<script>
import Navigation from "../components/Navigation";
import FooterNew from "../components/FooterNew.vue";
import {
  toggle_navigation_on_scroll,
  click_listener,
  doms,
  update_scroll,
  add_class_on_focus,
} from "@/assets/scripts/dom_utils";

export default {
  components: {
    Navigation,
    FooterNew,
    // Footer,
  },
  mounted: () => {
    toggle_navigation_on_scroll();
    click_listener("nav .link", () => {
      doms("nav input").forEach((dom) => {
        dom.checked = false;
      });
    });
    add_class_on_focus({
      [".faded_out"]: "fade_in",
    });
  },
};
</script>

<style>
html {
  font-family: "Graphik", sans;
  line-height: 1.6;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
