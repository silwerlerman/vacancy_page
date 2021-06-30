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
  name: "vacancy-tasks",
  components: { VacancyDevider },
  props: {
    tasks: {
      type: Array,
    },
  },
};
</script>

<style lang="scss" scoped>
.item__label {
  margin: 0px;
  font-size: 15px;
  line-height: 24px;
  margin-right: 4px;
}

.tasks {
  &__title {
    margin: 0px;
  }
  &__item {
    margin: 0px;
    padding-left: 25px;
  }
}
</style>