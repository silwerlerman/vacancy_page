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
      v-bind:iconColor="color"
    />
    <div class="items__link">
      <el-link
        v-bind:style="{ color: color }"
        class="items__link"
        type="primary"
        v-bind:href="href"
        >headhunter</el-link
      >
    </div>
    <Icon
      class="items__icon-right"
      v-if="hasRightIcon"
      iconName="Link"
      v-bind:iconColor="color"
    />
  </div>
</template>
<script>
import Icon from "./Icon";
export default {
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
  components: { Icon },
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
<style scoped>
.link__items {
  display: flex;
}
.items__link {
  display: flex;
  padding-top: 1px;
}
.el-link--primary {
  border-bottom-color: #57a2e8;
  margin-right: 0px;
  border-bottom: 1px solid currentColor;
}
.el-link--primary.is-underline:hover:after {
  border-bottom: 0px solid currentColor;
}
</style>