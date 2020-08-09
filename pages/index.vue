<template>
  <div>
    <div class="wave-container">
      <div class="hero-container">
        <div class="grid hero-grid">
          <vs-row justify="center">
            <vs-col xs="12" lg="6">
              <div class='hero-body'>
                <h2>Personal Investment</h2>
                <h3>Blog</h3>
                <p>Providing free open source tools and writing down my investment thoughts.</p>
              </div>
            </vs-col>
            <vs-col xs="12" lg="6">
              <div class="hero-img-container">
                <img class='hero-image' src="~/static/undraw_investing_7u74.svg" />
              </div>
            </vs-col>
          </vs-row>
        </div>
      </div>
      <div class='wave-svg'>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
          <path fill="#5b3cc4" fill-opacity="1" d="M0,320L21.8,293.3C43.6,267,87,213,131,213.3C174.5,213,218,267,262,288C305.5,309,349,299,393,282.7C436.4,267,480,245,524,229.3C567.3,213,611,203,655,202.7C698.2,203,742,213,785,229.3C829.1,245,873,267,916,261.3C960,256,1004,224,1047,218.7C1090.9,213,1135,235,1178,218.7C1221.8,203,1265,149,1309,160C1352.7,171,1396,245,1418,282.7L1440,320L1440,0L1418.2,0C1396.4,0,1353,0,1309,0C1265.5,0,1222,0,1178,0C1134.5,0,1091,0,1047,0C1003.6,0,960,0,916,0C872.7,0,829,0,785,0C741.8,0,698,0,655,0C610.9,0,567,0,524,0C480,0,436,0,393,0C349.1,0,305,0,262,0C218.2,0,175,0,131,0C87.3,0,44,0,22,0L0,0Z"></path>
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuesaxLogo from '~/components/VuesaxLogo.vue'

export default {
  components: {
    Logo,
    VuesaxLogo
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start()

      setTimeout(() => this.$nuxt.$loading.finish(), 5000)
    })
  }
}
</script>

<style>

.hero-grid {
  z-index: 5;
}
.hero-img-container {
  max-width: 350px;
  max-height: 220px;
  margin: auto;
}

.hero-body {
  margin: auto;
  padding: 1px 6px;
  text-align: right;
}
.hero-image {
  max-width: 100%;
}
@media (min-width: 768px) and (max-width: 979px) {
  .hero-image {
    right: 100px;
  }
}

.hero-container {
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding-bottom: 25px;
  margin-bottom: -1px;
  z-index: 10;
}
@media (min-width: 769px) {
  .hero-container {
    margin-top: 125px;
  }
}
@media (max-width: 768px) {
  .hero-container {
    margin-top: 100px;
  }
  .img-container {
    margin-top: 50px;
  }
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 55px;
  color: #35495e;
  letter-spacing: 1px;
  text-transform: capitalize;
  margin: 25px 0;
}

.subtitle {
  font-weight: 300;
  font-size: 1.1rem;
  color: #526488;
  word-spacing: 2px;
  padding-bottom: 15px;
  max-width: 600px;
}

.subtitle a {
  font-weight: 500;
  color: inherit;
}

.links {
  padding-top: 15px;
  margin-bottom: 20px;
}

.content-logos {
  display: flex;
  align-items: center;
  justify-content: center;
  min-width: 500px;
}

.plus {
  font-size: 2.5rem;
  margin: 15px;
  color: #35495e;
}

.h3 {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-weight: 400;
  margin: 10px;
}

.wave-container {
  background: #5b3cc4;
  color: #FFF;
  text-align: center;
  overflow: hidden;
}

.wave-svg {
  position: relative;
  background-color: white;
  display: block;
  transform-origin: bottom;
  margin-top: -100px;
  z-index: 1;
}

@keyframes wave {
  0% {
    margin-left: 0;
  }
  10% {
    margin-left: -200px;
  }
  40% {
    margin-left: -400px;
  }
  60% {
    margin-left: -200px;
  }
  75% {
    margin-left: -300px;
  }
  95% {
    margin-left: -50px;
  }
  100% {
    margin-left: -5px;
  }
}


.wave-svg > svg:nth-of-type(1) {
  animation: wave 7s cubic-bezier( 0.36, 0.45, 0.63, 0.53) infinite;
}


</style>
