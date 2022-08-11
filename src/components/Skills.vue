<template>
  <div id="skills" class="skills">
    <div :class="isShown ? '' : 'space'" style="padding: 0"></div>
    <section class="texts" v-if="isShown">
      <h1>Skills</h1>
      <img src="./../assets/work.png" alt="Working" />
      <article class="desk">
        <p>Some skills I've developed over time</p>
      </article>
    </section>
    <section v-if="isShown">
      <div class="tools">
        <div class="a box"></div>
        <div class="b box"></div>
        <div class="c box"></div>
        <div class="d box"></div>
        <div class="e box"></div>
        <div class="f box"></div>
        <div class="g box"></div>
      </div>
    </section>
    <article v-if="isShown" class="mob">
      <p>This are some of the tools that I work with</p>
    </article>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShown: false,
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
      const el = document.querySelector(".skills");
      const rect = el.getBoundingClientRect();
      if (this.isShown === true) {
        return (
          rect.top >= -650 &&
          rect.bottom <=
            700 + (window.innerHeight || document.documentElement.clientHeight)
        );
      } else {
        return (
          rect.top >= -500 &&
          rect.left >= 0 &&
          rect.bottom <=
            400 +
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
@media (max-width: 600px) {
  .space {
    margin-top: 458px;
  }
  h1 {
    font-size: 2.8rem;
    padding-bottom: 10px;
  }
  p {
    margin-top: 00px;
  }
  img {
    display: none;
  }
  .skills {
    flex-direction: column;
  }
  .desk {
    display: none;
  }
  .tools {
    gap: 7px;
    grid-template-columns: repeat(4, 65px);
    grid-template-rows: repeat(4, 65px);
  }
}
@media (min-width: 600px) and (max-width: 1200px) {
  .space {
    margin-top: 650px;
  }
  .desk {
    display: none;
  }
  p {
    margin-top: 20px;
  }
  h1 {
    font-size: 2.8rem;
    padding-bottom: 10px;
  }
  img {
    display: none;
  }
  .skills {
    flex-direction: column;
    height: 650px;
  }
  .tools {
    gap: 15px;
    grid-template-columns: repeat(4, 100px);
    grid-template-rows: repeat(4, 100px);
  }
}
@media (min-width: 1200px) {
  .space {
    margin-top: 600px;
  }
  .tools {
    gap: 15px;
    grid-template-columns: repeat(4, 100px);
    grid-template-rows: repeat(4, 100px);
  }
  .mob {
    display: none;
  }
  h1 {
    font-size: 3.5rem;
    padding-bottom: 40px;
  }
  .skills {
    height: 600px;
  }
  p {
    margin-top: 20px;
  }
}
@keyframes boxUp {
  from {
    transform: translateY(-200px);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
@keyframes boxDown {
  from {
    transform: translateY(200px);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
@keyframes boxLeft {
  from {
    transform: translateX(-200px);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
@keyframes boxRight {
  from {
    transform: translateX(200px);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
.skills {
  padding: 50px;
  display: flex;
  align-items: center;
  justify-content: space-around;
  background-color: #a77abf;

  box-shadow: inset 0em 0em 2em 0.5em rgba(0, 0, 0, 0.25);
}
h1 {
  text-align: center;
}
.texts,
.mob {
  animation: boxLeft 2s ease-out forwards;
}
.tools {
  display: grid;
  margin-top: 20px;
  color: rgb(245, 245, 245);
}
.mob {
  padding-top: 20px;
  padding-bottom: 10px;
}
p {
  text-align: center;
  inline-size: 300px;
  overflow-wrap: break-word;
  font-weight: 600;
  font-size: 1.3rem;
}
.box {
  border-radius: 20px;
  text-transform: uppercase;
  font-weight: 800;
  box-shadow: 10px 10px 8px rgba(0, 0, 0, 0.07);
}
.a {
  animation: boxLeft 1.5s ease-out forwards;
  background-image: url("./../assets/Js.png");
  background-size: 100%;
  grid-column: 1/3;
  grid-row: 1/3;
}
.b {
  animation: boxUp 2s ease-out forwards;
  background-image: url("./../assets/boot.png");
  background-size: 100%;
  grid-column: 3/4;
  grid-row: 1/2;
}
.c {
  animation: boxRight 1.5s ease-out forwards;
  background-image: url("./../assets/css.png");
  background-size: 100%;
  grid-column: 3/4;
  grid-row: 2/3;
}
.d {
  animation: boxRight 1.3s ease-out forwards;
  background-image: url("./../assets/nuxtt.png");
  background-size: 100%;
  grid-column: 2/3;
  grid-row: 3/4;
}
.e {
  animation: boxUp 1.75s ease-out forwards;
  background-image: url("./../assets/html.png");
  background-size: 100%;
  grid-column: 3/4;
  grid-row: 3/4;
}
.f {
  animation: boxDown 2.5s ease-out forwards;
  background-image: url("./../assets/vuetify.png");
  background-size: 100%;
  grid-column: 4/5;
  grid-row: 3/4;
}
.g {
  animation: boxLeft 3s ease-out forwards;
  background-image: url("./../assets/vue.png");
  background-size: 100%;
  grid-column: 3/4;
  grid-row: 4/5;
}
</style>
