<template>
  <div>
    <VacancyDevider deviderSize="24" />
    <h3 class="department__title">Информация о месте выхода</h3>
    <VacancyDevider deviderSize="12" />
    <div
      class="department__item"
      v-for="(item, index) in department"
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
      department: [
        {
          label: "Бизнес Юнит",
          value: "ВРМ",
        },
        {
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

<style scoped>
.department__title {
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
.department__item {
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