<template>
  <header class="header">
    <div class="btnsarea" id="desk">
      <section>
        <img alt="Logo" src="./../assets/logo.png" class="logo" />
      </section>
      <section class="buttons">
        <span @click="scrollTo(0)">Home</span>
        <span @click="scrollTo(700)">About</span>
        <span @click="scrollTo(1450)">Skills</span>
        <span @click="scrollTo(2100)">Portfolio</span>
        <div class="divider"></div>
        <span @click="scrollTo(2400)">Contact Me</span>
        <div class="drawer" @click="openDrawer()">
          <i class="fa fa-solid fa-bars"></i>
        </div>
      </section>
    </div>
    <div class="mob">
      <div
        :class="drawer ? 'animation1' : 'none'"
        class="bg1"
        @click="openDrawer()"
      ></div>
      <div :class="drawer ? 'animation2' : 'none'" class="bg2">
        <h2 @click="scrollTo(0)">Home</h2>
        <h2 @click="scrollTo(700)">About</h2>
        <h2 @click="scrollTo(1350)">Skills</h2>
        <h2 @click="scrollTo(1950)">Portfolio</h2>
        <h2 @click="scrollTo(2500)">Contact Me</h2>
      </div>
    </div>
    <section class="gradient"></section>
  </header>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      sizeScreen: null,
      lastScrollTop: 0,
    };
  },
  created() {
    window.addEventListener("scroll", this.navBar);
  },
  methods: {
    openDrawer() {
      this.drawer = !this.drawer;
    },
    scrollTo(sect) {
      this.drawer = false;
      window.scrollTo(0, sect);
    },
    navBar() {
      const navbar = document.getElementById("desk");
      let scrollTop = window.pageYOffset || document.documentElement.scrollTop;
      if (scrollTop > this.lastScrollTop) {
        navbar.style.top = "-80px";
      } else {
        navbar.style.top = "0px";
        navbar.style["padding-top"] = "10px";
      }
      navbar.classList.toggle("back", window.scrollY > 500);
      this.lastScrollTop = scrollTop;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@media (max-width: 699px) {
  .bg1 {
    position: fixed;
    top: 0;
    width: 120vw;
    height: 100vh;
    z-index: 20;
    background-color: rgba(255, 0, 221, 0.5);
    transform: translateX(100vw);
    transition: 1.5s;
  }
  h2 {
    margin-top: 30px;
    font-size: 1.8rem;
    color: #e90fc4;
  }
  .bg2 {
    position: fixed;
    top: 0;
    display: flex;
    flex-direction: column;
    text-align: center;
    padding-top: 30px;
    align-content: center;
    right: 0;
    width: 65vw;
    height: 100vh;
    z-index: 21;
    background-color: #152837;
    transform: translateX(66vw);
    transition: 1.2s;
  }
  .animation1 {
    transform: translateX(-10vw);
  }
  .animation2 {
    transform: translateX(0vw);
  }
  span,
  .divider {
    display: none;
  }
  .logo {
    max-width: 60px;
    margin-left: 15%;
    margin-top: 2px;
  }
  .drawer {
    font-size: 2.4rem;
    margin-right: 20px;
  }
  /* .header {
    padding: 15px 15px;
  } */
}
@media (max-width: 850px) and (min-width: 700px) {
  .bg1,
  .bg2,
  .drawer {
    display: none;
  }
  span {
    font-size: 1.3rem;
    margin-right: 20px;
  }
  .divider {
    margin-right: 10px;
    margin-left: -10px;
  }
  .logo {
    max-width: 50px;
    margin-left: 15%;
    margin-top: 2px;
  }
  /* .header {
    padding: 15px 15px;
  } */
}
@media (max-width: 1280px) and (min-width: 850px) {
  .bg1,
  .bg2,
  .drawer {
    display: none;
  }
  span {
    font-size: 1.4rem;
    margin-right: 40px;
  }
  .divider {
    margin-right: 20px;
    margin-left: -20px;
  }
  .logo {
    max-width: 70px;
    margin-left: 15%;
  }
  /* .header {
    padding: 15px 15px;
  } */
}
@media (min-width: 1280px) {
  .bg1,
  .bg2,
  .drawer {
    display: none;
  }
  span {
    font-size: 1.6rem;
    margin-right: 60px;
  }
  .divider {
    margin-right: 30px;
    margin-left: -30px;
  }
  .logo {
    max-width: 80px;
    margin-left: 1700%;
  }
  /* .header {
    padding: 20px 30px;
  } */
}
.btnsarea {
  align-items: center;
  justify-content: space-between;
}
.mob,
.btnsarea {
  position: fixed;
  z-index: 20;
  display: flex;
  width: 90.4%;
  transition: 0.5s;
}
.back {
  background: #6952a0;
}
.divider {
  height: 50px;
  border-right: solid 4px #6952a0;
}
.buttons {
  display: flex;
  align-items: center;
}
span {
  position: relative;
  cursor: pointer;
  font-weight: 600;
}
h2::after,
span::after {
  position: absolute;
  content: "";
  top: 100%;
  left: 0;
  width: 100%;
  height: 3px;
  background: #6952a0;
  transform: scaleX(0);
  transform-origin: right;
  transition: transform 0.5s;
}

h2:hover,
span:hover {
  transition: 1s;
}

h2:hover::after,
span:hover::after {
  transform: scaleX(1);
  transform-origin: left;
}
@keyframes has-shown {
  from {
    transform: translateX(40vw);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
h2 {
  opacity: 0;
}
.animation2 :nth-child(1) {
  animation: has-shown 1s ease-out forwards;
  animation-delay: 0.3s;
}
.animation2 :nth-child(2) {
  animation: has-shown 1s ease-out forwards;
  animation-delay: 0.6s;
}
.animation2 :nth-child(3) {
  animation: has-shown 1s ease-out forwards;
  animation-delay: 0.9s;
}
.animation2 :nth-child(4) {
  animation: has-shown 1s ease-out forwards;
  animation-delay: 1.2s;
}
.animation2 :nth-child(5) {
  animation: has-shown 1s ease-out forwards;
  animation-delay: 1.5s;
}
.header {
  position: relative;
  height: 500px;
  background: linear-gradient(180deg, #a77abf 10%, #313262 100%);
}
</style>
