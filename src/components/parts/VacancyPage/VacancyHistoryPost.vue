<template>
  <div>
    <div class="header__messages">
      <div v-for="(item, index) in history" :key="index">
        <div v-if="showDate(item.date)">
          <VacancyDevider deviderSize="32" />
          <Tag :text="item.date" />
          <VacancyDevider deviderSize="12" />
        </div>
        <HistoryListMessege :message="item" />
      </div>
    </div>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
import HistoryListMessege from "@/components/elements/HistoryListMessege";
import Tag from "@/components/elements/Tag";
export default {
  name: "vacancy-historypost",
  components: { VacancyDevider, HistoryListMessege, Tag },
  props: {
    history: {
      type: Array,
    },
  },
  methods: {
    showDate: function (value) {
      let lastDate = localStorage.getItem("lastDate");
      if (lastDate === null) {
        localStorage.setItem("lastDate", value);
        lastDate = value;
        return true;
      } else if (lastDate !== value) {
        localStorage.setItem("lastDate", value);
        lastDate = value;
        return true;
      } else return false;
    },
  },
  mounted() {
    localStorage.removeItem("lastDate");
  },
};
</script>

<style lang="scss" scoped>
.header__messages {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
}
.el-tag {
  border-radius: 12px;
  font-weight: 400;
  font-size: 16px;
  padding: 0px 10px;
}
</style>