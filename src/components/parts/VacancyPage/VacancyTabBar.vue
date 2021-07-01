<template>
  <div class="vacancy-tabs">
    <VacancyDevider deviderSize="40" />
    <el-tabs v-model="activeName">
      <el-tab-pane label="История" name="history"
        ><VacancyHistoryPost :history="history"
      /></el-tab-pane>
      <el-tab-pane label="Документы" name="documents"></el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
import VacancyHistoryPost from "@/components/parts/VacancyPage/VacancyHistoryPost";
export default {
  data() {
    return {
      activeName: "history",
    };
  },
  name: "vacancy-tabs",
  components: { VacancyDevider, VacancyHistoryPost },
  props: {
    history: Array,
  },
};
</script>

<style lang="scss" scoped>
.el-tabs {
  & ::v-deep &__item {
    font-size: 18px;
    font-weight: bold;
    color: $black-400;
    margin: -10px 0px 7px 0px;
    &.is-active {
      color: $blue-600;
    }
  }
  & ::v-deep &__active-bar {
    background-color: $blue-600;
    height: 4px;
  }
  & ::v-deep &__header {
    margin: 0px;
  }
  & ::v-deep &__nav-wrap::after {
    height: 1px;
  }
}

.vacancy-tabs {
  font-size: 18px;
}

.is-active {
  font-size: 18px;
}
</style>