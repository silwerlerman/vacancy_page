<template>
  <div>
    <VacancyDevider deviderSize="24" />
    <h3 class="conditions__title">Основные условия</h3>
    <VacancyDevider deviderSize="12" />
    <div
      class="conditions__item"
      v-for="(item, index) in conditions"
      :key="index"
    >
      <p class="item__label">{{ item.label }}:</p>
      <p class="item__value">{{ item.value }}</p>
    </div>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
export default {
  data() {
    return {
      conditions: [
        {
          label: "Оклад",
          value: "80000 до 100000 р.",
        },
        {
          label: "Бонусы",
          value: "10%",
        },
        {
          label: "Опыт работы",
          value: "Опыт от 0 лет",
        },
        {
          label: "Потребность",
          value: "5 человек",
        },
      ],
    };
  },
  name: "vacancy-conditions",
  components: { VacancyDevider },
};
</script>

<style>
.conditions__title {
  margin: 0px;
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
.conditions__item {
  display: flex;
  flex-direction: row;
}
.item__label {
  margin: 0px;
  font-size: 14px;
  line-height: 24px;
  margin-right: 4px;
}
.item__value {
  margin: 0px;
  font-size: 14px;
  line-height: 24px;
  color: #2d81ce;
}
</style>