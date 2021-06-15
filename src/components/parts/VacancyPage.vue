<template>
  <div class="vacancy-page">
    <VacancyHeader />
    <VacancyDevider deviderSize="24" hasLine />
    <div class="vacancy-page__competencies flex-between">
      <VacancyCompetencies />
      <p class="competencies__update">Последние изменения: {{ lastUpdate }}</p>
    </div>
    <VacancyConditions />
    <VacancyDepartment />
    <VacancyTeam />
    <VacancyLink />
  </div>
</template>

<script>
import VacancyHeader from "./VacancyHeader";
import VacancyDevider from "@/components/elements/VacancyDevider";
import VacancyCompetencies from "./VacancyCompetencies";
import VacancyConditions from "./VacancyConditions";
import VacancyDepartment from "./VacancyDepartment";
import VacancyTeam from "./VacancyTeam";
import VacancyLink from "./VacancyLink";
export default {
  data() {
    return {
      lastUpdate: "25.05.2021",
    };
  },
  name: "vacancy-page",
  components: {
    VacancyHeader,
    VacancyDevider,
    VacancyCompetencies,
    VacancyConditions,
    VacancyDepartment,
    VacancyTeam,
    VacancyLink,
  },
};
</script>

<style>
.competencies__update {
  padding-top: 25px;
  margin: 0px 0px 0px -70px;
  color: #9e9e9e;
  min-width: 257px;
  max-height: 21px;
}
.vacancy-page {
  background: #ffffff;
  border-radius: 12px;
  padding: 40px;
  margin: 20px;
  max-width: 720px;
  word-wrap: break-word;
}
.vacancy-page__competencies {
  display: flex;
  flex-direction: row;
}
.flex-between {
  justify-content: space-between;
}
</style>