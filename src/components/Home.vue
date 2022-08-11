<template>
  <div class="home">
    <section class="text">
      <p>FrontEnd</p>
      <p>Developer</p>
      <h4 :class="isShown ? '' : 'space'">
        "The only way to do great work is to love what you do"
      </h4>
    </section>
    <section v-if="isShown">
      <img src="./../assets/shinobu2.png" alt="home img" class="img" />
    </section>
    <section class="balls">
      <div class="line line1" v-if="isShown"></div>
      <div class="line line2" v-if="isShown"></div>
      <div class="ball"></div>
      <div class="glassBall ball2"></div>
      <div class="glassBall ball3"></div>
      <div class="glassBall ball4"></div>
      <div class="square square1" v-if="isShown"></div>
      <div class="square square2" v-if="isShown"></div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShown: true,
    };
  },
  created() {
    window.addEventListener("scroll", this.scroll);
  },
  methods: {
    async scroll() {
      this.isShown = await this.isInViewport();
    },
    isInViewport() {
      const el = document.querySelector(".home");
      const rect = el.getBoundingClientRect();
      if (this.isShown === true) {
        return (
          rect.top >= -300 &&
          rect.bottom <=
            0 + (window.innerHeight || document.documentElement.clientHeight)
        );
      } else {
        return (
          rect.top >= -100 &&
          rect.left >= 0 &&
          rect.bottom <=
            (window.innerHeight || document.documentElement.clientHeight) &&
          rect.right <=
            (window.innerWidth || document.documentElement.clientWidth)
        );
      }
    },
  },
};
</script>

<style scoped>
.home {
  margin-top: -250px;
  margin-bottom: 300px;
  position: relative;
  display: flex;
  justify-content: space-between;
}
.glassBall {
  background: rgba(255, 255, 255, 0.15);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  backdrop-filter: blur(10.5px);
  -webkit-backdrop-filter: blur(10.5px);
  border: 1px solid rgba(255, 255, 255, 0.18);
  position: absolute;
  border-radius: 50%;
}
.square {
  position: absolute;
}
@media (max-width: 599px) {
  .line1 {
    width: 600px;
    left: 54%;
    top: -40px;
  }
  .line2 {
    width: 600px;
    right: 35%;
    top: 280px;
  }
  .square1 {
    border: solid 2px #152837;
    width: 10px;
    height: 10px;
    top: -35.5px;
    left: 65%;
  }
  .square1::before { /* É os quadradinhos do header */
    content: "";
    position: absolute;
    top: -10px;
    left: 8px;
    width: 12px;
    height: 12px;
    background-color: #4b366e;
  }
  .square2 {
    border: solid 2px #152837;
    width: 10px;
    height: 10px;
    top: 265px;
    left: 50%;
  }
  .square2::before {
    content: "";
    position: absolute;
    top: 8px;
    left: 80%;
    width: 12px;
    height: 12px;
    background-color: #04d7a2;
  }
  .ball {
    left: -30px;
    top: 0px;
    width: 220px;
    height: 220px;
  }
  .ball4 {
    width: 60px;
    height: 60px;
    top: 130px;
    right: 10%;
  }
  .ball3 {
    width: 80px;
    height: 80px;
    top: 185px;
    left: 20%;
  }
  .ball2 {
    width: 175px;
    height: 175px;
    top: -38px;
    left: 5%;
  }
  .img {
    width: 0px;
  }
  .home {
    justify-content: center;
  }
  .text {
    text-align: center;
    justify-content: center;
    align-content: center;
  }
  h4 {
    font-size: 1rem;
    inline-size: 220px;
    margin: auto;
  }
  p {
    font-size: 3.5rem;
    font-weight: 900;
  }
}
.line {
  position: absolute;
  border-bottom: solid 2px #152837;
  height: 1px;
}
@media (min-width: 600px) {
  .text {
    margin-left: 10%;
  }
  .square1 {
    border: solid 2px #152837;
    width: 10px;
    height: 10px;
    top: 65px;
    left: 65%;
  }
  .square1::before {
    content: "";
    position: absolute;
    top: -10px;
    left: 8px;
    width: 12px;
    height: 12px;
    background-color: #dca9d4;
  }
  .square2 {
    border: solid 2px #152837;
    width: 10px;
    height: 10px;
    top: 265px;
    left: 43%;
  }
  .square2::before {
    content: "";
    position: absolute;
    top: 8px;
    left: 80%;
    width: 12px;
    height: 12px;
    background-color: #dca9d4;
  }
  .line1 {
    width: 1200px;
    left: 60%;
    top: 60px;
  }
  .line2 {
    width: 400px;
    left: 20%;
    top: 280px;
  }
  .ball4 {
    width: 60px;
    height: 60px;
    top: 320px;
    left: 20%;
  }
  .ball3 {
    width: 100px;
    height: 100px;
    top: 220px;
    left: 5%;
  }
  .ball2 {
    width: 300px;
    height: 300px;
    top: -70px;
    left: 5%;
  }
  .img {
    width: 0px;
  }
  .ball {
    top: -20px;
    width: 350px;
    left: -70px;
    height: 350px;
  }
  h4 {
    font-size: 1rem;
    overflow-wrap: break-word;
    inline-size: 220px;
  }
  p {
    font-size: 3rem;
    font-weight: 700;
  }
}
@media (min-width: 960px) {
  .space {
    margin-bottom: 40px;
  }
  .line1 {
    top: -40px;
  }
  .square1 {
    top: -35px;
  }
  .img {
    width: 400px;
    opacity: 0;
  }
  .ball {
    width: 400px;
    top: -40px;
    height: 400px;
  }
  .ball2 {
    width: 350px;
    height: 350px;
  }
  .ball3 {
    top: 255px;
  }
  .ball4 {
    top: 330px;
    left: 15%;
  }

  h4 {
    font-size: 1rem;
    inline-size: 280px;
  }
  p {
    font-size: 3.8rem;
  }
}
@media (min-width: 1280px) {
  .space {
    margin-bottom: 64.24px;
  }
  .img {
    width: 500px;
    opacity: 0;
  }
  .line2 {
    top: 320px;
    width: 800px;
    left: 5%;
  }
  .square2 {
    top: 305px;
  }
  h4 {
    font-size: 1.2rem;
  }
  p {
    font-size: 4.4rem;
  }
}
.ball {
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(90deg, #152837 5%, #3f256e 100%);
}
@keyframes bouncing {
  from {
    transform: translateY(13px);
  }
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
@keyframes has-shownL1 {
  from {
    transform: translateX(40vw);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
.line1,
.square1 {
  animation: has-shownL1 1.5s ease-in-out forwards;
}
.line2,
.square2 {
  animation: has-shownL2 1.5s ease-in-out forwards;
}
@keyframes has-shownL2 {
  from {
    transform: translateX(-40vw);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
img {
  animation: has-shown 2s ease-out forwards;
  animation-delay: 0.5s;
}
.ball2 {
  animation: bouncing 5s ease-in-out infinite alternate;
}
.ball3 {
  animation: bouncing 4s ease-in-out infinite alternate;
}
.ball4 {
  animation: bouncing 2.5s ease-in-out infinite alternate;
}
.text {
  z-index: 1;
}
h4 {
  margin-top: 10px;
  font-weight: 500;
  overflow-wrap: break-word;
}
p {
  font-family: "Gentium Book Basic", serif;
  text-shadow: 0 10px 7px rgba(0, 0, 0, 0.07);
}
</style>
