<template>
  <el-tag
    effect="plain"
    :class="{
      disabled: disabled,
      big: size === 'big',
      medium: size === 'medium',
      small: size === 'small',
    }"
    :closable="closable"
  >
    {{ text }}</el-tag
  >
</template>
<script>
export default {
  name: "Tag",
  props: {
    text: {
      type: String,
      default: "Новый тэг",
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: "medium",
    },
    closable: {
      type: Boolean,
      default: false,
    },
    hasIcon: {
      type: Boolean,
      default: false,
    },
    iconName: {
      type: String,
      default: "Work",
    },
  },
};
</script>
<style lang="scss" scoped>
.el-tag {
  border-color: $black-200;
  background: $black-100;
  color: $blue-500;
  font-size: 16px;
  border-radius: 12px;
  &:hover {
    background: $black-200;
  }
}

.disabled {
  background: $black-200;
  color: $black-500;
}

.big {
  height: 40px;
}

.medium {
  height: 32px;
}

.small {
  height: 24px;
}
</style>