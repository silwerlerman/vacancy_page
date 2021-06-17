<template>
  <div class="app">
    <VacancyPage />
    <RightPanel />
  </div>
</template>

<script>
import VacancyPage from "@/components/parts/VacancyPage/VacancyPage";
import RightPanel from "@/components/parts/RightPanel/RightPanel";
export default {
  name: "app",
  components: { VacancyPage, RightPanel },
};
</script>

<style>
.app {
  font-family: Arial;
  display: flex;
  flex-direction: row;
  justify-content: center;
  background-color: #f1f1f1;
}
</style>
