<template>
  <div>
    <VacancyDevider deviderSize="24" />
    <h3 class="department__title">Команда</h3>
    <VacancyDevider deviderSize="12" />
    <div
      class="department__item"
      v-for="(item, index) in team"
      :key="index + 1"
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
      team: [
        {
          label: "Директор БЮ",
          value: "Ангелина Петрова",
        },
        {
          label: "Директор проекта",
          value: "Александр Антонов",
        },
        {
          label: "Рекрутер",
          value: "Артем Павловичев",
        },
        {
          label: "Доп рекрутер",
          value: "Иван Павлюченко",
        },
      ],
    };
  },
  name: "vacancy-team",
  components: { VacancyDevider },
};
</script>

<style>
.department__title {
  margin: 0px;
}
.department__item {
  display: flex;
  flex-direction: row;
}
</style>