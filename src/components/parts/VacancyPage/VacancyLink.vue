<template>
  <div>
    <VacancyDevider deviderSize="24" hasLine />
    <VacancyDevider deviderSize="24" />
    <div class="link__items">
      <p class="item__label">Ссылка на источник резюме</p>
      <Link hasRightIcon :href="href" />
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
  props: {
    href: {
      type: String,
      default: "",
    },
  },
};
</script>

<style lang="scss" scoped>
.item__label {
  margin: 0px 5px 0px 0px;
  align-self: center;
}
.link__items {
  display: flex;
  flex-direction: row;
  justify-content: center;
  font-size: 15px;
  color: $black-500;
}
</style>