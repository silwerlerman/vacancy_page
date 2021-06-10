<template>
  <div class="vacancy-page">
    <VacancyHeader />
    <VacancyDevider deviderSize="24" hasLine="true" />
  </div>
</template>

<script>
import VacancyHeader from "./VacancyHeader";
import VacancyDevider from "@/components/elements/VacancyDevider";
export default {
  name: "vacancy-page",
  components: { VacancyHeader, VacancyDevider },
};
</script>

<style>
.vacancy-page {
  background: #ffffff;
  border-radius: 12px;
  padding: 40px;
  margin: 20px;
  max-width: 720px;
  word-wrap: break-word;
}
</style>