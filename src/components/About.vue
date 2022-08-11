<template>
  <div id="about" class="about">
    <section v-if="isShown">
      <div class="divimg">
        <img class="img" id="img" src="./../assets/me.jpeg" alt="eu" />
      </div>
    </section>
    <section v-if="isShown" class="has-shown" style="position: relative">
      <h1 class="title">About</h1>
      <article class="box">
        <p>
          Hello, my name is Douglas Noel. Nice to meet you! 
          Full-time student of
          System Analysis and Development and Electronic Engineering. Quiet and
          determined, always trying to get the best out of life. I'm currently
          working with JS and its current framework, but always looking to learn
          new things like C+. Lover of mathematics and everything it brings to
          the world!
        </p>
      </article>
    </section>
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
      const el = document.querySelector(".about");
      const rect = el.getBoundingClientRect();
      if (this.isShown === true) {
        return (
          rect.top >= -600 &&
          rect.bottom <=
            600 + (window.innerHeight || document.documentElement.clientHeight)
        );
      } else {
        return (
          rect.top >= -200 &&
          rect.left >= 0 &&
          rect.bottom <=
            200 +
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
  .about {
    margin-bottom: 50px;
  }
  .img {
    top: 250px;
    left: 25px;
    border-radius: 20px;
    border: solid 5px #a9cadc;
  }
  .title {
    font-size: 2.8rem;
    top: -35px;
  }
  p {
    font-size: 0.92rem;
  }
  .box {
    text-align: center;
    width: 260px;
    height: 225px;
    padding: 20px;
  }
}
@media (min-width: 600px) and (max-width: 1200px) {
  .img {
    border-radius: 0px 0px 30px 30px;
    top: 200px;
    left: 130px;
  }
  .box {
    width: 450px;
    height: 140px;
    padding: 40px;
  }
  .title {
    font-size: 2.8rem;
    top: -35px;
  }
  .box::before {
    top: -490px;
  }
}
@media (min-width: 1200px) {
  .about {
    margin-left: 210px;
  }
  .title {
    font-size: 3.5rem;
    top: -45px;
  }
  .img {
    border-radius: 30px 0px 30px 30px;
    top: 180px;
    left: -210px;
  }
  .box {
    width: 600px;
    height: 140px;
    padding: 50px;
  }
  p {
    font-size: 1.1rem;
  }
  .box::before {
    top: -590px;
  }
}
.box {
  position: relative;
  background-color: #76749b;
  border-radius: 25px;
  box-shadow: 0 32px 60px rgba(0, 0, 0, 0.07);
  overflow: hidden;
  transition: box-shadow 0.5s;
}
.box::before {
  content: "";
  position: absolute;
  left: -15%;
  width: 100%;
  height: 320%;
  background: linear-gradient(90deg, transparent, #7899aa33);
  transform: rotate(71deg);
  pointer-events: none;
  filter: blur(5px);
}
.divimg {
  position: relative;
}
.img {
  position: absolute;
  width: 300px;
  width: 250px;
  box-shadow: 5px 32px 20px rgba(0, 0, 0, 0.07);
  z-index: 1;
}
.about {
  display: flex;
  justify-content: center;
  height: 600px;
}
@media (min-width: 1400px) {
  .about {
    justify-content: end;
    margin-right: 10%;
  }
}
@keyframes has-shown {
  from {
    transform: translateY(40px);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
@keyframes has-shownI {
  from {
    transform: translateX(-100px);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
img {
  animation: has-shownI 2s ease-out forwards;
  opacity: 0;
}
.has-shown {
  animation: has-shown 2s ease-out forwards;
  opacity: 0;
}
.box:hover {
  box-shadow: 0 0 11px rgba(33, 33, 33, 0.2);
}
article {
  position: relative;
}
article .title {
  text-align: center;
}
.title {
  z-index: 1;
  position: absolute;
  left: 0;
  right: 0;
  text-align: center;
  overflow: visible;
}
.menu {
  display: flex;
  justify-items: center;
  justify-content: center;
}
</style>
