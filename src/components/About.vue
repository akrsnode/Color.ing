<template>
  <div class="boxwrapper">
    <div class="boxmodel">
      <img src="@/assets/profile.png">
      <h1>Hi, my name is Adrian.</h1>
      <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit.
      Aenean a placerat nisi, sed scelerisque diam.
      Phasellus non augue vel nisi elementum elementum.
      In dapibus hendrerit elit, a commodo velit convallis eget.
      </p>
      <div class="socialbar">
        <a id="item-left" href="mailto:vansmoe@hotmail.com"><img src="@/assets/mail.svg"></a>
        <a id="item-right" href="https://github.com/vansmoe"><img src="@/assets/git.svg"></a>
      </div>
    </div>
    <div class="homeme" @click="$emit('closeAbout')">
      <span class="undrln">home</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
};
</script>

<style lang="scss" scoped>
$animate: all 0.2 ease-in-out;

.boxwrapper {
  max-width: 400px;
  background-color: #FFF;
  font-family: 'Montserrat', sans-serif;
  position: absolute;
  bottom: 0;
  padding-bottom: 100px;

  @media (min-width: 401px) {
    background: #FFF;
    margin: 0 auto;
    position: inherit;
  }
}

.boxmodel {
  min-height: 380px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  color: #707070;
  margin: 0px 30px;

  @media (min-width: 401px) {
    padding-top: 10vh;
  }

  @media (min-height: 800px) {
    padding-top: 20vh;
  }
  img {
    height: 40vw;
    max-height: 180px;
    align-self: flex-start;
  }

  h1 {
    font-size: 15px;
    font-weight: 700;
    align-self: flex-end;
  }

  p {
    font-weight: 200;

  }
}

.socialbar {
  display: grid;
  width: 100%;
  color: #707070;
  grid-template-columns: 1fr 20px 50px 20px 1fr;

  #item-left {
    grid-column: 2 / span 1;
  }

  #item-right {
    grid-column: 4 / span 1;
  }

  a:hover {
    opacity: 0.5;
  }

  img {
    height: 20px;
    width: auto;
  }
}

.homeme {
  width: 72px;
  height: 20px;
  position: absolute;
  bottom: 0;
  right: 0;
  margin-bottom: 20px;
  margin-right: 20px;
  font-family: 'Montserrat', sans-serif;
  font-size: 15px;
  font-weight: 200;
  color: #707070;

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
      background-color: #707070;
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
