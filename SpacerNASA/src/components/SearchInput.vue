<template>
      <input 
      id="search" 
      name="search" 
      :value="value"
      @input="handleChange"
      :class="{dark}"/>
</template>

<script>
export default {
  name: "SearchInput",
  props: {
    value: {
      type: String,
      required: true
    },
    dark: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    handleChange(e) {
      this.$emit("input", e.target.value);
    }
  }
};
</script>

<style lang="scss" scoped>
input {
  display: flex;
  color: white;
  text-align: center;
  font-weight: 300;
  font-size: 18px;
  height: 30px;
  border: 0;
  border-bottom: 1px solid white;
  background: none;
  transition: box-shadow 0.3s;
  @media (min-width: 1024px) {
    font-weight: 400;
  }
}
input:focus {
  outline: none;
  box-shadow: 0 10px 20px -8px rgba(255, 255, 255, 0.6);
}
.dark {
  color: #1e3d4a;
  border-bottom-color: #1e3d4a;
}
.dark:focus {
  color: #1e3d4a;
  box-shadow: 0 10px 20px -8px rgba(30, 61, 74, 0.569);
}
</style>

