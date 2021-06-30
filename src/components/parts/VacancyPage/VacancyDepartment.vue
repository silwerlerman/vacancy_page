<template>
  <div>
    <VacancyDevider deviderSize="24" />
    <h3 class="department__title">Информация о месте выхода</h3>
    <VacancyDevider deviderSize="12" />
    <div
      class="department__item"
      v-for="(item, index) in departments"
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
  name: "vacancy-department",
  components: { VacancyDevider },
  props: {
    departments: {
      type: Array,
    },
  },
};
</script>

<style lang="scss" scoped>
.department {
  &__title {
    margin: 0px;
  }
  &__item {
    display: flex;
    flex-direction: row;
  }
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

.item {
  &__label {
    margin: 0px;
    font-size: 14px;
    line-height: 24px;
    margin-right: 4px;
    min-width: fit-content;
  }
  &__value {
    margin: 0px;
    font-size: 14px;
    line-height: 24px;
    color: $blue-600;
  }
}
</style>