<template>
  <div class="vacancy-page">
    <VacancyHeader />
  </div>
</template>

<script>
import VacancyHeader from "./VacancyHeader";
export default {
  name: "vacancy-page",
  components: { VacancyHeader },
};
</script>

<style>
.vacancy-page {
  background: #ffffff;
  border-radius: 12px;
  padding: 40px;
  margin: 20px;
}
</style>