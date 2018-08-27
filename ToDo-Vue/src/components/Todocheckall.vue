<template>
    <div>
            <label for="">
              <input 
              type="checkbox" 
              :checked="!anyRemaining"
              @change="allChecked"
              >
              Check All
            </label>
          </div>
</template>

<script>
export default {
  name: "Todocheckall",
  props: {
    anyRemaining: {
      type: Number,
      required: true
    }
  },
  methods: {
    allChecked() {
      eventBus.$emit("checkAllChanged", this.anyRemaining);
    }
  }
};
</script>

<style>
</style>
