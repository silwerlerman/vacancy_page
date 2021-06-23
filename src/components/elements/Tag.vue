<template>
  <el-tag
    effect="plain"
    v-bind:class="{
      disabled: disabled,
      big: size === 'big',
      medium: size === 'medium',
      small: size === 'small',
    }"
    v-bind:closable="closable"
  >
    {{ text }}</el-tag
  >
</template>
<script>
export default {
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
<style scoped>
.el-tag {
  border-color: #ececec;
  background: #faf9f9;
  color: #378bd8;
  font-size: 16px;
  border-radius: 12px;
}
.el-tag:hover {
  background: #ececec;
}
.disabled {
  background: #ececec;
  color: #9e9e9e;
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