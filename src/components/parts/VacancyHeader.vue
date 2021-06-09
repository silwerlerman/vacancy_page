<template>
  <div class="vacancy-header">
    <div class="header__area-top">
      <div class="header__tags"></div>
      <select class="header__dropdown">
        <option class="dropdown__option">Открыта</option>
        <option class="dropdown__option">Закрыта</option>
      </select>
    </div>
    <VacancyDevider40 />
    <h1 class="header__title">Ведущий специалист по тестированию</h1>
    <VacancyDevider24 />
    <div class="header__area-middle"></div>
    <VacancyDevider24 />
    <div class="header__area-bottom"></div>
  </div>
</template>

<script>
import VacancyDevider40 from "@/components/elements/deviders/VacancyDevider40";
export default {
  name: "vacancy-header",
  components: { VacancyDevider40 },
};
</script>

<style>
.vacancy-header {
  display: flex;
  flex-direction: column;
}
.header__area-top {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.header__title {
}
</style>