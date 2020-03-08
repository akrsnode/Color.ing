<template>
  <div class="logo">
    <div class="color">color</div>
    <div class="ing">ing</div>
  </div>
</template>

<script>
export default {
  name: 'Logo',
};
</script>

<style scoped lang="scss">
@import url('https://fonts.fontself.com/gE309jx/gilbert-color-bold-preview5.css');

.logo {
  font-family: 'gilbert-color-bold-preview5';
  font-size: 50px;
  padding-left: 25px;
  padding-top: 30px;
  display: flex;
  -webkit-filter: invert(100%);
  filter: invert(100%);
}

.ing {
  padding-left: 90px;
  padding-top: 30px;
  position: absolute;
}
</style>
