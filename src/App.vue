<template>
  <div class="app">
    <VacancyPage />
    <RightPanel />
  </div>
</template>

<script>
import VacancyPage from "@/components/parts/VacancyPage";
import RightPanel from "@/components/parts/RightPanel";
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
}
</style>
