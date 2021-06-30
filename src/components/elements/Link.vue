<template>
  <div
    @mouseenter="colorChangeToDarkBlue"
    @mouseleave="colorChangeToLightBlue"
    class="link__items"
  >
    <Icon
      class="items__icon-left"
      v-if="hasLeftIcon"
      iconName="Link"
      :iconColor="color"
    />
    <div class="items__link">
      <el-link :style="{ color: color }" type="primary" :href="href"
        >headhunter</el-link
      >
    </div>
    <Icon
      class="items__icon-right"
      v-if="hasRightIcon"
      iconName="Link"
      :iconColor="color"
    />
  </div>
</template>
<script>
import Icon from "./Icon";
export default {
  name: "Link",
  components: { Icon },
  data() {
    return {
      isOver: true,
      color: "#57a2e8",
    };
  },
  props: {
    text: {
      type: String,
      default: "Новая ссылка",
    },
    hasLeftIcon: {
      type: Boolean,
      default: false,
    },
    hasRightIcon: {
      type: Boolean,
      default: false,
    },
    iconColor: {
      type: String,
      default: "#57a2e8",
    },
    href: {
      type: String,
      default: "",
    },
  },

  methods: {
    colorChangeToDarkBlue: function () {
      this.color = "#1767b1";
    },
    colorChangeToLightBlue: function () {
      this.color = "#57a2e8";
    },
  },
};
</script>
<style lang="scss" scoped>
.link__items {
  display: flex;
}
.items__link {
  display: flex;
  padding-top: 1px;
}
.el-link--primary {
  border-bottom-color: $blue-400;
  margin-right: 0px;
  border-bottom: 1px solid currentColor;
  &.is-underline:hover:after {
    border-bottom: 0px solid currentColor;
  }
}
</style>