<template>
  <div class="vacancy-skills">
    <VacancyDevider deviderSize="24" />
    <h3 class="skills__title">Желательные навыки</h3>
    <VacancyDevider deviderSize="12" />
    <div class="header__tags">
      <Tag
        v-for="(tag, index) in skillTags"
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
  props: {
    skillTags: {
      type: Array,
    },
  },
  name: "vacancy-skills",
  components: { VacancyDevider, Tag },
};
</script>

<style scoped>
.skills__title {
  margin: 0px;
}
.vacancy-skills {
  max-width: 660px;
}
.vacancy-header {
  display: flex;
  flex-direction: column;
}
.header__tags {
  display: flex;
  flex-direction: row;
}
.tags__item {
  margin-right: 8px;
}
.el-tag {
  border-radius: 12px;
  font-family: Arial;
  font-weight: 400;
  font-size: 16px;
  padding: 0px 10px;
}
.tags__item {
  margin-right: 8px;
}
</style>