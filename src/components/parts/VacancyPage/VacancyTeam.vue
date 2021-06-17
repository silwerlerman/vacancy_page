<template>
  <div>
    <VacancyDevider deviderSize="24" />
    <h3 class="team__title">Команда</h3>
    <VacancyDevider deviderSize="12" />
    <div class="team__item" v-for="(item, index) in team" :key="index + 1">
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

<style scoped>
.team__title {
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
.team__item {
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