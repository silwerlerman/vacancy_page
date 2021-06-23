<template>
  <div class="panel-tabs">
    <el-menu
      default-active="0"
      mode="horizontal"
      text-color="#C0C0C0"
      active-text-color="#2d81ce"
      @select="handleSelect"
    >
      <el-menu-item index="0">Подбор</el-menu-item>
      <el-menu-item index="1">Комментарии</el-menu-item>
    </el-menu>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tabToShow: "0",
    };
  },
  name: "panel-tabs",
  methods: {
    handleSelect(key) {
      this.tabToShow = key;
    },
  },
};
</script>

<style scoped>
.panel-tabs {
  font-size: 18px;
}
.is-active {
  font-size: 18px;
}
.el-tabs__header {
  margin-bottom: 0px !important;
}
.el-menu {
  margin-top: 10px;
}
.el-menu-item {
  font-size: 18px;
  font-weight: bold;
  margin-right: 15px;
  margin-left: 25px;
}
.el-menu-item.is-active {
  font-size: 18px;
}
.el-menu-item:hover {
  font-size: 18px;
}
.el-menu--horizontal > .el-menu-item {
  border-bottom: 4px solid #409eff;
  padding: 0px;
}
</style>