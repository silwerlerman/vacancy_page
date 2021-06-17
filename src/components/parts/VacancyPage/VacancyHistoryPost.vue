<template>
  <div class="vacancy-history">
    <div class="header__messages">
      <div v-for="(mes, index) in history" :key="index">
        <div v-if="showDate(mes.date)">
          <VacancyDevider deviderSize="32" />
          <el-tag type="info">{{ mes.date }}</el-tag>
          <VacancyDevider deviderSize="12" />
        </div>
        <HistoryListMessege v-bind:message="mes" />
      </div>
    </div>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
import HistoryListMessege from "@/components/elements/HistoryListMessege";
export default {
  data() {
    return {
      history: [
        {
          date: "25.05.2021",
          author: "Артем Павловичев",
          type: "AddCandidate",
          text: "К вакансии добавлен кандидат",
          name: "Иванов Дмитрий",
        },
        {
          date: "25.05.2021",
          author: "Артем Павловичев",
          type: "FieldUpdate",
          text: "Обновлено значение поля",
          fieldName: "Статус",
          oldValue: "Новая",
          newValue: "Открыта",
        },
        {
          date: "25.05.2021",
          author: "Артем Павловичев",
          type: "VacancyCreate",
          text: "Создана вакансия",
          name: "Новая",
        },
      ],
    };
  },
  name: "vacancy-historypost",
  components: { VacancyDevider, HistoryListMessege },
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

<style scoped>
.vacancy-history {
}
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
.el-tabs__header {
  margin-bottom: 0px !important;
}
</style>