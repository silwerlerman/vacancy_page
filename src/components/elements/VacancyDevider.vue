<template>
  <div
    :class="{ 'horizontal-line': hasLine }"
    :style="{ height: deviderSize + 'px' }"
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

<style lang="scss" scoped>
.horizontal-line {
  border-bottom: 1px solid $black-300;
}
</style>