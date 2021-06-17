<template>
  <div class="vacancy-competencies">
    <VacancyDevider deviderSize="24" />
    <h3 class="competencies__title">Ключевые навыки</h3>
    <VacancyDevider deviderSize="12" />
    <div class="header__tags">
      <el-tag class="tags__item" type="info">CMS на PHP</el-tag>
      <el-tag class="tags__item" type="info">GIT</el-tag>
    </div>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
export default {
  name: "vacancy-competencies",
  components: { VacancyDevider },
};
</script>

<style scoped>
.competencies__title {
  margin: 0px;
}
.vacancy-competencies {
  max-width: 530px;
}
.vacancy-header {
  display: flex;
  flex-direction: column;
}
.header__tags {
  display: flex;
  flex-direction: row;
  max-width: 530px;
  flex-wrap: wrap;
}
.tags__item {
  margin-right: 8px;
}
.el-tag {
  border-radius: 12px;
  font-family: Arial;
  font-weight: 400;
  font-size: 16px;
  padding: 0px 10px;
}
</style>