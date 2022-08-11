<template>
  <div id="portfolio" class="portfolio" :class="isShown ? '' : 'space'">
    <section class="text" v-if="isShown">
      <h1>Portfolio</h1>
      <p>
        Currently I have worked for multiple companies as a freelancer working
        with FrontEnd Dev, creating responsive and intuitive pages for the user.
        Previously, I worked leading teams at AIESEC Brazil, as Vice President
        business to business. I also have courses in mathematics at Harvard
        university. Linkedin on footer for more informations.
      </p>
    </section>
    <section class="imagebox" v-if="isShown">
      <img src="./../assets/coding.png" alt="Coding" />
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
      const el = document.querySelector(".portfolio");
      const rect = el.getBoundingClientRect();
      if (this.isShown === true) {
        return (
          rect.top >= -600 &&
          rect.bottom <=
            750 + (window.innerHeight || document.documentElement.clientHeight)
        );
      } else {
        return (
          rect.top >= -500 &&
          rect.left >= 0 &&
          rect.bottom <=
            250 +
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
    margin-bottom: 726px;
  }
  p {
    font-size: 0.92rem;
    inline-size: 290px !important;
  }
  h1 {
    font-size: 2.8rem;
  }
  .portfolio {
    flex-direction: column;
    align-items: center;
  }
  img {
    width: 300px;
    animation: has-shownI 4s ease-out forwards !important;
  }
}
@media (min-width: 600px) and (max-width: 1000px) {
  .space {
    margin-top: 718px;
  }
  .portfolio {
    flex-direction: column;
    align-items: center;
  }
  h1 {
    font-size: 2.8rem;
  }
  img {
    animation: has-shownI 4s ease-out forwards !important;
  }
}
@media (min-width: 1000px) and (max-width: 1200px) {
  .space {
    margin-top: 427px;
  }
  h1 {
    font-size: 2.8rem;
  }
  .text {
    padding: 15px;
  }
}
@media (min-width: 1200px) {
  .space {
    margin-top: 427px;
  }
  h1 {
    font-size: 3.5rem;
  }
  p {
    font-size: 1.1rem;
  }
  .text {
    padding: 40px;
  }
}
@keyframes has-shown {
  from {
    transform: translateX(-300px);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
@keyframes has-shownI {
  from {
    transform: translateX(300px);
    opacity: 0;
  }
  to {
    opacity: 1;
    transform: none;
  }
}
img {
  animation: has-shownI 2s ease-out forwards;
}

.portfolio {
  display: flex;
  justify-content: center;
  padding-bottom: 100px;
}
h1 {
  text-align: center;
}
.text {
  animation: has-shown 2s ease-out forwards;
  margin-top: 100px;
}
.imagebox {
  margin-top: 80px;
}
p {
  text-align: center;
  margin-top: 20px;
  inline-size: 550px;
  overflow-wrap: break-word;
}
</style>
