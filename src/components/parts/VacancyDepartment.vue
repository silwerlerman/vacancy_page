<template>
  <div class="vacancy-department">
    <VacancyDevider deviderSize="24" />
    <h3 class="department__title">Информация о месте выхода</h3>
    <VacancyDevider deviderSize="12" />
    <div class="department__item" v-for="item in conditions" :key="item.id">
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
          id: 1,
          label: "Проект",
          value: "ВТБ МСБ",
        },
        {
          id: 2,
          label: "Бизнес Юнит",
          value: "ВРМ",
        },
        {
          id: 3,
          label: "Опыт работы",
          value: "BPM/Практика BPM/ECM/SOA, Отдел разработки ВРМ и SOA",
        },
      ],
    };
  },
  name: "vacancy-department",
  components: { VacancyDevider },
};
</script>

<style>
.department__title {
  margin: 0px;
}
.vacancy-department {
  max-width: 530px;
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
.department__item {
  display: flex;
  flex-direction: row;
}
</style>