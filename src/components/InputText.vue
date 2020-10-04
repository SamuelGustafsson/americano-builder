<template>
  <input
    class="effect-4"
    type="text"
    placeholder="Placeholder Text"
    @input="onInput"
    @keydown.enter="onKeydownEnter"
  />
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    text: String
  },
  methods: {
    onInput(e: any) {
      this.$emit("update:modelValue", e.target.value);
    },
    onKeydownEnter(e: any) {
      this.$emit("keydown-enter", e.target.value);
    }
  }
});
</script>

<style scoped lang="scss">
input {
  font: 15px/24px "Lato", Arial, sans-serif;
  color: #333;
  width: 100%;
  box-sizing: border-box;
  letter-spacing: 1px;
  max-width: 400px;

  border: 0;
  padding: 5px 0 7px;
  border: 1px solid transparent;
  border-bottom-color: #ccc;
  transition: 0.4s;

  .focus-border {
    position: absolute;
    height: 0;
    bottom: 0;
    left: 0;
    width: 100%;
    transition: 0.4s;
    z-index: -1;
  }

  &:focus {
    padding: 5px 14px 7px;
    transition: 0.4s;

    .focus-border {
      transition: 0.4s;
      height: 36px;
      border: 2px solid #3399ff;
      z-index: 1;
    }
  }
}
</style>
