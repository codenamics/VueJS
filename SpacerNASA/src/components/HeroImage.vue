<template>
    <img class="heroImage"/>
</template>

<script>
export default {
  name: "HeroImage"
};
</script>

<style lang="scss" scoped>
.heroImage {
  background-image: url("../assets/hero.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 40% 0%;
  height: 100vh;
  width: 100%;
  position: fixed;
  z-index: -1;
}
</style>

