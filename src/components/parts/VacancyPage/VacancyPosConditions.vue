<template>
  <div>
    <VacancyDevider deviderSize="24" />
    <h3 class="pos-conditions__title">Должностные требования</h3>
    <VacancyDevider deviderSize="12" />
    <ul class="pos-conditions__item">
      <li
        class="item__label"
        v-for="(item, index) in posConditions"
        :key="index"
      >
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
export default {
  props: {
    posConditions: {
      type: Array,
    },
  },
  name: "vacancy-pos-conditions",
  components: { VacancyDevider },
};
</script>

<style scoped>
.pos-conditions__title {
  margin: 0px;
}
.pos-conditions__item {
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