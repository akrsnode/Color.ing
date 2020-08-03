<template>
  <div id="app" :style="{ backgroundColor: value, color: value }">
    <Logo v-if="loading === false" />
    <Loader v-if="loading === true" />
    <Home v-if="aboutOpen === false && loading === false" v-on:inputChange="handleChange" />
    <About v-if="aboutOpen" @closeAbout="aboutOpen = false" />
    <div class="about-btn" v-if="aboutOpen === false" @click="handleAboutOpen">
      <span class="undrln">about.me</span>
    </div>
  </div>
</template>

<script>
import Logo from './components/Logo.vue';
import Home from './components/Home.vue';
import About from './components/About.vue';
import Loader from './components/Loader.vue';

export default {
  name: 'App',
  components: {
    Logo,
    Home,
    About,
    Loader,
  },
  data() {
    return {
      loading: true,
      aboutOpen: false,
      value: '',
    };
  },
  mounted() {
    setTimeout(this.handleLoading, 2000);
    console.log(this.loading);
  },
  methods: {
    handleAboutOpen() {
      this.aboutOpen = true;
    },
    handleChange(event) {
      const { value } = event.target;
      this.value = value;
    },
    handleLoading() {
      this.loading = false;
    },
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200;400;700&family=Playfair+Display&display=swap');

$animate: all 0.2 ease-in-out;

body {
  margin: 0;
  padding: 0;
}

#app {
  height: 100vh;
  color: #FFF;
}

.about-btn {
  width: 72px;
  height: 20px;
  position: absolute;
  bottom: 0;
  right: 0;
  padding-bottom: 20px;
  padding-right: 20px;
  font-family: 'Montserrat', sans-serif;
  font-size: 15px;
  font-weight: 200;
  -webkit-filter: invert(100%);
  filter: invert(100%);
  opacity: 0.7;

  .undrln {
    transition: $animate;
    position: absolute;
    &:before {
      content: "";
      position: absolute;
      bottom: -1px;
      width: 0px;
      height: 1px;
      transition: $animate;
      transition-duration: 0.75s;
      opacity: 0;
      background-color: pink;
      left: 0;
    }
  }
  &:hover {
    cursor: pointer;
    .undrln {
      &:before {
        width: 100%;
        opacity: 1;
      }
    }
  }
}
</style>
