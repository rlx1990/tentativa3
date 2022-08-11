<template>
  <div id="app">
    <Header />
    <Home />
    <About />
    <Skills />
    <Portfolio />
    <Contact />
    <Svgs />
    <Svgs-r />
  </div>
</template>

<script>
import Home from "./components/Home.vue";
import Header from "./components/Header.vue";
import About from "./components/About.vue";
import Skills from "./components/Skills.vue";
import Portfolio from "./components/Portfolio.vue";
import Contact from "./components/Contact.vue";
import Svgs from "./components/Svgs.vue";
import SvgsR from "./components/SvgsR.vue";
/* import { mapActions } from "vuex"; */

export default {
  name: "App",
  components: {
    Home,
    Header,
    About,
    Skills,
    Portfolio,
    Contact,
    Svgs,
    SvgsR,
  },
};
</script>

<style>
#app {
  z-index: 10;
  background-color: #403e70;
  margin: 0px 4.8%;
  margin-bottom: 50px;
  overflow: hidden;
}
/* É o fundo ao lado, as bordas */
body {
  color: #ffffff;
  background-color: #301537;
  -webkit-text-size-adjust: none;
}
* {
  scroll-behavior: smooth;
  margin: 0px;
  padding: 0px;
  font-family: "Montserrat", sans-serif;
  font-weight: 500;
}
</style>
