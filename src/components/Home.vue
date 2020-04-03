<template>
  <div class="banner">
    <div id="displayText">
      {{ textDisplay }}
      <input
        type="text"
        placeholder="color"
        v-on:input="(event) => this.$emit('inputChange', event)">
    .</div>
  </div>
</template>

<script>
/* eslint-disable */

const textSample = ['It’s all about', 'I like this', 'What a gorgeous', 'The style is nice, but do you have it in a different'];
const [textSample0, textSample1, textSample2, textSample3, textSample4] = textSample;
let displayText = '';

function chooseText() {
  if (performance.navigation.type === 1) {
    displayText = textSample[Math.floor(Math.random() * 4)];
  } else {
    displayText = textSample0;
  }
}
chooseText();
console.log(displayText);
/* eslint-enable */

export default {
  name: 'Home',
  props: {
    backgroundColor: String,
  },
  data() {
    return {
      textDisplay: displayText,
    };
  },
};
</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css?family=Playfair+Display&display=swap');

.banner {
  font-family: 'Playfair Display', serif;
  font-size: 60px;
  margin-left: 25px;
  display: flex;
  align-items: flex-end;
  flex-direction: row;
  margin-top: 350px;
  -webkit-filter: invert(100%);
  filter: invert(100%);

  @media (min-width: 1024px) {
    margin-left: 100px;
    font-size: 100px;
  }

  input {
    font-family: 'Playfair Display', serif;
    font-size: 60px;
    color:  #E7E7E7;
    border: none;
    border-bottom: 4px solid #707070;
    background: none;
    max-width: 250px;
    text-align: center;

    @media (min-width: 1024px) {
      border-bottom: 6px solid #707070;
      max-width: 400px;
      font-size: 100px;
    }
  }
}
.banner:hover {
  opacity: 0.5;
}

</style>
