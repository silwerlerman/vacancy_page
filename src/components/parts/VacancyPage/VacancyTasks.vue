<template>
  <div>
    <VacancyDevider deviderSize="24" />
    <h3 class="tasks__title">Обязанности и задачи</h3>
    <VacancyDevider deviderSize="12" />
    <ul class="tasks__item">
      <li class="item__label" v-for="(item, index) in tasks" :key="index + 1">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
export default {
  props: {
    tasks: {
      type: Array,
    },
  },
  name: "vacancy-tasks",
  components: { VacancyDevider },
};
</script>

<style scoped>
.tasks__title {
  margin: 0px;
}
.tasks__item {
  margin: 0px;
  padding-left: 25px;
}
.item__label {
  margin: 0px;
  font-size: 15px;
  line-height: 24px;
  margin-right: 4px;
}
</style>