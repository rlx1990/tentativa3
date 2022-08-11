<template>
  <div id="contact" class="contact" :class="isShown ? '' : 'space'">
    <section v-if="isShown">
      <h1>Contact me</h1>
    </section>
    <section class="sect" v-if="isShown">
      <div class="img">
        <img src="./../assets/logo.png" alt="" />
        <ul>
          <li>
            <a href="mailto:dg_soares@live.com">
              <i class="fa fa-envelope"></i>
            </a>
          </li>
          <li>
            <a href="tel:+55 (81) 997184305">
              <i class="fa fa-phone"></i>
            </a>
          </li>
          <li>
            <a
              href="https://www.linkedin.com/in/douglas-soares-0bb144200/"
              target="_blank"
            >
              <i class="fa fa-linkedin"></i>
            </a>
          </li>
          <li>
            <a href="https://github.com/rlx1990" target="_blank">
              <i class="fa fa-github"></i>
            </a>
          </li>
        </ul>
      </div>
      <div class="text">
        <p>
          If you have any doubts, please do not hesitate to contact , your
          message will be very welcome!
        </p>
        <div class="place">
          <div class="placeicon">
            <i class="fas fa-map-marker-alt"></i>
          </div>
          Paulista, Pernambuco - Brazil
        </div>
      </div>
    </section>
    <section class="footer">
      <p>Designed by</p>
      <p>Douglas Soares</p>
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
      const el = document.querySelector(".contact");
      const rect = el.getBoundingClientRect();
      if (this.isShown === true) {
        return (
          rect.top >= 0 &&
          rect.bottom <=
            400 + (window.innerHeight || document.documentElement.clientHeight)
        );
      } else {
        return (
          rect.top >= 0 &&
          rect.left >= 0 &&
          rect.bottom <=
            150 +
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
@media (max-width: 700px) {
  .space {
    min-height: 400.516px;
  }
  .contact {
    padding: 30px 0px 50px 0px;
  }
  .img {
    margin: auto;
  }
  li {
    margin: 10px;
  }
  ul {
    display: flex;
    margin-bottom: 20px;
  }
  .text {
    inline-size: 300px;
    margin: auto;
    overflow-wrap: break-word;
  }
  p {
    font-size: 0.9rem;
  }
  h1 {
    font-size: 2.4rem;
  }
  .place {
    font-size: 0.7rem;
  }
  .sect {
    display: flex;
    flex-direction: column;
    margin-top: 30px;
    padding-bottom: 20px;
  }
}
@media (min-width: 700px) and (max-width: 1280px) {
  .space {
    min-height: 319px;
  }
  p {
    font-size: 1.2rem;
  }
  .text {
    inline-size: 340px;
    overflow-wrap: break-word;
  }
  h1 {
    font-size: 2.8rem;
  }
  .contact {
    padding: 30px 10px 50px 10px;
  }
}
@media (min-width: 1280px) {
  .space {
    min-height: 338px;
  }
  p {
    font-size: 1.3rem;
  }
  h1 {
    font-size: 3.5rem;
  }
  .text {
    inline-size: 400px;
    overflow-wrap: break-word;
  }
  .contact {
    padding: 50px;
  }
}
@media (min-width: 700px) {
  .sect {
    display: flex;
    justify-content: space-around;
    margin-top: 50px;
    padding-bottom: 30px;
  }
  li {
    margin-left: 10px;
  }
  ul {
    display: flex;
    margin-top: 30px;
  }
}
@keyframes has-shown {
  from {
    opacity: 0;
    transform: translateY(50px);
  }
  to {
    opacity: 1;
    transform: none;
  }
}
.text {
  animation: has-shown 2s ease-out forwards;
  animation-delay: 400ms;
  opacity: 0;
}
.img {
  animation: has-shown 2s ease-out forwards;
  animation-delay: 400ms;
  opacity: 0;
}

h1 {
  animation: has-shown 2s ease-out forwards;
}
.contact {
  justify-content: center;
  text-align: center;
  background: linear-gradient(180deg, #a77abf 10%, #424077 100%);
  /* background: #a77abf; */
  position: relative;
}
.footer {
  position: absolute;
  right: 0;
  left: 0;
  bottom: 0px;
  background-color: #424077;
}
a {
  color: #ffffff; /* simbolos do contact */
}
li {
  transition: 0.6s;
  color: #04d7a2;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #152837;
  height: 30px;
  width: 30px;
  border-radius: 80px;
  list-style: none;
  box-shadow: 0 5px 4px rgba(0, 0, 0, 0.3);
}
li:hover {
  transition: 0.6s;
  transform: translateY(-10px);
}
li:nth-child(1):hover a {
  color: #e4405f;
  transition: 0.6s;
}
li:nth-child(2):hover a {
  color: #25d366;
  transition: 0.6s;
}
li:nth-child(3):hover a {
  color: #0a66c2;
  transition: 0.6s;
}
li:nth-child(4):hover a {
  transition: 0.6s;
  color: #007bb6;
}
.place {
  font-size: 1.1rem;
  margin-top: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.placeicon {
  margin-right: 10px;
  display: flex;
  background-color: #152837;
  border-radius: 50%;
  align-items: center;
  justify-content: center;
  height: 30px;
  width: 30px;
  color: #ffffff;
  box-shadow: 0 5px 4px rgba(0, 0, 0, 0.3);
}

img {
  width: 100px;
}
</style>
