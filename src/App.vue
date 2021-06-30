<template>
  <div class="app">
    <div class="wrapper">
      <div class="content">
        <div><VacancyPage /></div>
        <div><RightPanel /></div>
      </div>
    </div>
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

<style lang="scss">
.app {
  font-family: Arial;
  background-color: $black-100;
}
body {
  margin: 0;
  padding: 0;
}
.wrapper {
  max-width: 1200px;
  margin: 0 auto;
}
.content {
  display: flex;
  flex-direction: row;
}
</style>
