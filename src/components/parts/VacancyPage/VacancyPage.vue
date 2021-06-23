<template>
  <div class="vacancy-page">
    <VacancyHeader />
    <VacancyDevider deviderSize="24" hasLine />
    <div class="vacancy-page__competencies flex-between">
      <VacancyCompetencies v-bind:tags="competenciesTags" />
      <p class="competencies__update">Последние изменения: {{ lastUpdate }}</p>
    </div>
    <VacancyConditions v-bind:conditions="conditions" />
    <VacancyDepartment v-bind:departments="departments" />
    <VacancyTeam v-bind:teamMembers="teamMembers" />
    <VacancyLink v-bind:href="hhHref" />
    <VacancySkills v-bind:skillTags="skillTags" />
    <VacancyPosConditions v-bind:posConditions="posConditions" />
    <VacancyTasks v-bind:tasks="tasks" />
    <VacancyTabBar v-bind:history="history" />
  </div>
</template>

<script>
import VacancyHeader from "./VacancyHeader";
import VacancyDevider from "@/components/elements/VacancyDevider";
import VacancyCompetencies from "./VacancyCompetencies";
import VacancyConditions from "./VacancyConditions";
import VacancyDepartment from "./VacancyDepartment";
import VacancyTeam from "./VacancyTeam";
import VacancyLink from "./VacancyLink";
import VacancySkills from "./VacancySkills";
import VacancyPosConditions from "./VacancyPosConditions";
import VacancyTasks from "./VacancyTasks";
import VacancyTabBar from "./VacancyTabBar";
export default {
  data() {
    return {
      lastUpdate: "25.05.2021",
      competenciesTags: ["CMS на PHP", "GIT"],
      conditions: [
        {
          id: 1,
          label: "Оклад",
          value: "80000 до 100000 р.",
        },
        {
          id: 2,
          label: "Бонусы",
          value: "10%",
        },
        {
          id: 3,
          label: "Опыт работы",
          value: "Опыт от 0 лет",
        },
        {
          id: 4,
          label: "Потребность",
          value: "5 человек",
        },
      ],
      departments: [
        {
          label: "Бизнес Юнит",
          value: "ВРМ",
        },
        {
          label: "Опыт работы",
          value: "BPM/Практика BPM/ECM/SOA, Отдел разработки ВРМ и SOA",
        },
      ],
      teamMembers: [
        {
          label: "Директор БЮ",
          value: "Ангелина Петрова",
        },
        {
          label: "Директор проекта",
          value: "Александр Антонов",
        },
        {
          label: "Рекрутер",
          value: "Артем Павловичев",
        },
        {
          label: "Доп рекрутер",
          value: "Иван Павлюченко",
        },
      ],
      hhHref: "https://headhunter.ru",
      skillTags: [
        "Data Center Architecture",
        "Spring (All)",
        "Node.js",
        "Computer science",
        "ReactJS",
      ],
      posConditions: [
        "Знание PHP, SQL, HTML, CSS",
        "Опыт работы c Git Понимание принципов MVC, знание фреймворков",
        "Желание учиться и развиваться",
        "Будет плюсом: Опыт работы с CMS на PHP",
      ],
      tasks: ["Разработка проектов на платформе SiuteCRM"],
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
  name: "vacancy-page",
  components: {
    VacancyHeader,
    VacancyDevider,
    VacancyCompetencies,
    VacancyConditions,
    VacancyDepartment,
    VacancyTeam,
    VacancyLink,
    VacancySkills,
    VacancyPosConditions,
    VacancyTasks,
    VacancyTabBar,
  },
};
</script>

<style scoped>
.competencies__update {
  padding-top: 25px;
  margin: 0px 0px 0px -70px;
  color: #9e9e9e;
  min-width: 257px;
  max-height: 21px;
}
.vacancy-page {
  background: #ffffff;
  border-radius: 12px;
  padding: 40px;
  margin: 20px 0px;
  max-width: 720px;
  word-wrap: break-word;
}
.vacancy-page__competencies {
  display: flex;
  flex-direction: row;
}
.flex-between {
  justify-content: space-between;
}
</style>