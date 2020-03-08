<template>
  <div id="app" :style="{
    color: backgroundColor,
    backgroundColor: backgroundColor
    }">
    <Logo />
    <Home v-if="aboutOpen === false"/>
    <About v-if="aboutOpen" @closeAbout="aboutOpen = false" />
    <div v-if="aboutOpen === false" class="aboutme" @click="handleAboutOpen">about.me</div>
  </div>
</template>

<script>
import Logo from './components/Logo.vue';
import Home from './components/Home.vue';
import About from './components/About.vue';

export default {
  name: 'App',
  components: {
    Logo,
    Home,
    About,
  },
  data() {
    return {
      aboutOpen: false,
      aboutItem: null,
    };
  },
  methods: {
    handleAboutOpen() {
      this.aboutOpen = true;
    },
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200;400;700&family=Playfair+Display&display=swap');

body {
  margin: 0;
}

#app {
  padding: 0;
  margin: 0;
  height: 100vh;
  color: #FFF;
}

.aboutme {
  font-family: 'Montserrat', sans-serif;
  color: #707070;
  font-size: 15px;
  position: absolute;
  bottom: 0;
  right: 0;
  margin-bottom: 20px;
  margin-right: 20px;
}
.aboutme:hover {
    text-decoration: underline;
}

</style>
