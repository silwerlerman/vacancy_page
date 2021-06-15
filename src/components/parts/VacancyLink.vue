<template>
  <div>
    <VacancyDevider deviderSize="24" hasLine />
    <VacancyDevider deviderSize="24" />
    <div class="link__items">
      <p class="item__label">Ссылка на источник резюме</p>
      <Link hasRightIcon />
    </div>
    <VacancyDevider deviderSize="24" hasLine />
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
import Link from "@/components/elements/Link";
export default {
  name: "vacancy-link",
  components: { VacancyDevider, Link },
};
</script>

<style>
.department__title {
  margin: 0px;
}
.link__items {
  display: flex;
  flex-direction: row;
  justify-content: center;
  font-size: 15px;
  color: #9e9e9e;
}
</style>