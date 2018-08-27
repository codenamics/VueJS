<template>
    <div :style="style" class="item"></div>
</template>

<script>
export default {
  name: "Item",
  props: {
    item: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      photo: this.item.links[0].href,
      title: this.item.links[0].href
    };
  },
  computed: {
    style() {
      return `background-image: url("${this.photo}")`;
    }
  }
};
</script>

<style lang="scss" scoped>
.item {
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50%;
  width: 70vw;
  height: 250px;
  @media (min-width: 768px) {
    width: 25vw;
  }
}
</style>

