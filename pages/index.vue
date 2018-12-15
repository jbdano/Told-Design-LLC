<template>
  <div id="app">
    <TopNavigation/>
    <home-hero/>
    <div class="home-main-container">
      <OurProcess/>
      <TeamOverview/>
      <OurTeam/>
      <TestimonialOverview/>
      <Testimonials/>
      <Contact/>
      <Footer/>
    </div>
  </div>
</template>

<script>
import jQuery from "jquery";

if (process.browser) {
  window.jQuery = jQuery;
  window.$ = jQuery;
  require("bootstrap");
}

import TopNavigation from "~/components/TopNavigation.vue";
import HomeHero from "~/components/HomeHero.vue";
import OurProcess from "~/components/OurProcess.vue";
import TeamOverview from "~/components/TeamOverview.vue";
import OurTeam from "~/components/OurTeam.vue";
import TestimonialOverview from "~/components/TestimonialOverview.vue";
import Testimonials from "~/components/Testimonials.vue";
import Contact from "~/components/Contact.vue";
import Footer from "~/components/Footer.vue";

export default {
  name: "app",
  components: {
    TopNavigation,
    HomeHero,
    OurProcess,
    TeamOverview,
    OurTeam,
    TestimonialOverview,
    Testimonials,
    Contact,
    Footer
  }
};
</script>

<style lang="scss">
html,
body {
  overflow-x: hidden;
  margin: 0px !important;
  background-color: #e5e5e5;
}

.theme-color-green {
  color: #50ada2;
}

.theme-color-white {
  color: #fcfaf9;
}

.theme-inline-button {
  display: inline-block;
  padding: 20px 10px;
  text-decoration: none;
  border-radius: 5px;
  border: 3px solid #50ada2;
  font-size: 14px;
  transition: all 0.3s ease-out;

  &:hover {
    background-color: #50ada2;
    color: #fcfaf9;
    text-decoration: none;
    cursor: pointer;
  }
  &:focus {
    outline: 0;
  }
}

.theme-inline-button-primary {
  background-color: #50ada2;
  color: rgba(0, 0, 0, 0.5);
}

.theme-inline-button-secondary {
  background-color: transparent;
  color: #50ada2;
}

h1,
h2,
h3,
h4,
h5,
p,
a {
  font-family: "Josefin Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  text-rendering: optimizeLegibility;
  color: #3c4858;
  line-height: 1.1;
  margin: 0;
}

h1 {
  font-size: calc(46px + (80 - 46) * ((100vw - 300px) / (1600 - 300)));
  margin: 0;
  font-weight: bold;
}

h3 {
  font-size: calc(24px + (30 - 24) * ((100vw - 300px) / (1600 - 300)));
  margin: 0;
  font-weight: bold;
}

h4 {
  font-size: calc(21px + (24 - 21) * ((100vw - 300px) / (1600 - 300)));
  margin: 0;
  font-weight: bold;
}

h5 {
  font-size: calc(18px + (24 - 18) * ((100vw - 300px) / (1600 - 300)));
  margin: 0;
  font-weight: bold;
}

p,
a,
q,
li {
  font-size: calc(16px + (18 - 16) * ((100vw - 300px) / (1600 - 300)));
  line-height: 1.5;
  color: #999999;
  margin-bottom: 15px;
}

.home-main-container {
  position: relative;
  margin: -50px 15px 0px 15px;
  border-radius: 6px 6px 0px 0px;
  background-color: #fcfaf9;
  box-shadow: 0 16px 24px 2px rgba(0, 0, 0, 0.14),
    0 6px 30px 5px rgba(0, 0, 0, 0.12), 0 8px 10px -5px rgba(0, 0, 0, 0.2);
}
</style>
