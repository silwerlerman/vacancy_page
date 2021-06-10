<template>
  <div
    v-bind:class="{ 'horizontal-line': hasLine }"
    v-bind:style="{ height: deviderSize + 'px' }"
  />
</template>

<script>
export default {
  name: "vacancy-devider",
  props: {
    deviderSize: {
      type: String,
      default: "24",
    },
    hasLine: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style>
.horizontal-line {
  border-bottom: 1px solid #e2e2e2;
}
</style>