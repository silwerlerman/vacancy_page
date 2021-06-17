<template>
  <div class="vacancy-tabs">
    <VacancyDevider deviderSize="40" />
    <el-tabs>
      <el-tab-pane label="История"><VacancyHistoryPost /></el-tab-pane>
      <el-tab-pane label="Документы"></el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
import VacancyHistoryPost from "@/components/parts/VacancyPage/VacancyHistoryPost";
export default {
  name: "vacancy-tabs",
  components: { VacancyDevider, VacancyHistoryPost },
};
</script>

<style scoped>
.vacancy-tabs {
  font-size: 18px;
}
.is-active {
  font-size: 18px;
}
</style>