<template>
  <div class="vacancy-tabs">
    <VacancyDevider deviderSize="40" />
    <el-menu
      default-active="0"
      mode="horizontal"
      text-color="#C0C0C0"
      active-text-color="#2d81ce"
      @select="handleSelect"
    >
      <el-menu-item index="0">История</el-menu-item>
      <el-menu-item index="1">Документы</el-menu-item>
    </el-menu>
    <VacancyHistoryPost v-if="tabToShow === '0'" :history="history" />
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
import VacancyHistoryPost from "@/components/parts/VacancyPage/VacancyHistoryPost";
export default {
  name: "vacancy-tabs",
  components: { VacancyDevider, VacancyHistoryPost },
  props: {
    history: Array,
  },
  data() {
    return {
      tabToShow: "0",
    };
  },
  methods: {
    handleSelect(key) {
      this.tabToShow = key;
    },
  },
};
</script>

<style lang="scss" scoped>
.vacancy-tabs {
  font-size: 18px;
}

.is-active {
  font-size: 18px;
}

.el {
  &-tabs__header {
    margin-bottom: 0px !important;
  }
  &-menu {
    margin-top: -20px;
    &-item {
      font-size: 18px;
      font-weight: bold;
      margin-right: 40px;
      &.is-active {
        font-size: 18px;
      }
      &:hover {
        font-size: 18px;
      }
    }
    &--horizontal > &-item {
      border-bottom: 4px solid $blue-600;
      padding: 0px;
    }
  }
}
</style>