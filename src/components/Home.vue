<template>
  <div class="banner">
    <div class="">Choose your own <input v-model="backgroundColor" placeholder="color" />.</div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      backgroundColor: '',
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
