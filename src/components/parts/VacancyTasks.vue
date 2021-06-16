<template>
  <div>
    <VacancyDevider deviderSize="24" />
    <h3 class="tasks__title">Должностные требования</h3>
    <VacancyDevider deviderSize="12" />
    <ul class="tasks__item">
      <li
        class="item__label"
        v-for="(item, index) in conditions"
        :key="index + 1"
      >
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
export default {
  data() {
    return {
      conditions: ["Разработка проектов на платформе SiuteCRM"],
    };
  },
  name: "vacancy-pos-conditions",
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