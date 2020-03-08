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
        <a id="item-left" href=""><img src="@/assets/mail.svg"></a>
        <a id="item-right" href=""><img src="@/assets/git.svg"></a>
      </div>
    </div>
    <div class="homeme" @click="$emit('closeAbout')">home</div>
  </div>
</template>

<script>
export default {
  name: 'About',
};
</script>

<style lang="scss" scoped>
.boxwrapper {
  max-width: 400px;
  background-color: #FFF;
  font-family: 'Montserrat', sans-serif;

  @media (min-width: 401px) {
    background: #FFF;
    margin: 0 auto;
  }
}

.boxmodel {
  min-height: 380px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  color: #707070;
  margin: 150px 30px 0px 30px;

  img {
    height: 40vw;
    max-height: 250px;
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
  color: #707070;
  font-weight: 200;
  font-size: 15px;
  position: absolute;
  bottom: 0;
  right: 0;
  margin-bottom: 20px;
  margin-right: 20px;

  &:hover {
    text-decoration: underline;
    font-style: italic;
  }
}
</style>
