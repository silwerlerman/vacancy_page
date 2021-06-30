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
        :text="tag"
      />
    </div>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
import Tag from "@/components/elements/Tag";
export default {
  name: "vacancy-skills",
  components: { VacancyDevider, Tag },
  props: {
    skillTags: {
      type: Array,
    },
  },
};
</script>

<style lang="scss" scoped>
.el-tag {
  border-radius: 12px;
  font-family: Arial;
  font-weight: 400;
  font-size: 16px;
  padding: 0px 10px;
}

.header__tags {
  display: flex;
  flex-direction: row;
  flex-flow: row wrap;
  margin-top: -8px;
}

.tags__item {
  margin-top: 8px;
  margin-right: 8px;
}

.skills__title {
  margin: 0px;
}

.vacancy {
  &-skills {
    max-width: 660px;
  }
  &-header {
    display: flex;
    flex-direction: column;
  }
}
</style>