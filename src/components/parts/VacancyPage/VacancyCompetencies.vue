<template>
  <div class="vacancy-competencies">
    <VacancyDevider deviderSize="24" />
    <h3 class="competencies__title">Ключевые навыки</h3>
    <VacancyDevider deviderSize="12" />
    <div class="header__tags">
      <Tag
        v-for="(tag, index) in tags"
        :key="index"
        class="tags__item"
        v-bind:text="tag"
      />
    </div>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
import Tag from "@/components/elements/Tag";

export default {
  name: "vacancy-competencies",
  props: {
    tags: {
      type: Array,
    },
  },
  components: { VacancyDevider, Tag },
};
</script>

<style scoped>
.competencies__title {
  margin: 0px;
}
.vacancy-competencies {
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
.tags__item {
  margin-right: 8px;
}
</style>