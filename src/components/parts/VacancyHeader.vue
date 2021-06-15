<template>
  <div class="vacancy-header">
    <div class="header__area-top flex-between">
      <div class="header__tags">
        <el-tag v-if="isHard" type="info">Сложная вакансия</el-tag>
      </div>
      <el-select v-model="status" placeholder="Select" plain>
        <el-option
          v-for="item in options"
          :key="item.value"
          :label="item.label"
          :value="item.value"
        >
        </el-option>
      </el-select>
    </div>
    <VacancyDevider deviderSize="40" />
    <h1 class="header__title">{{ vacancyName }}</h1>
    <VacancyDevider deviderSize="24" />
    <div class="header__area-middle">
      <div
        class="area-middle__item"
        v-for="button in middleAreaButtons"
        :key="button.id"
      >
        <Button
          v-bind:iconName="button.iconName"
          v-bind:type="button.type"
          v-bind:text="button.text"
        />
      </div>
    </div>
    <VacancyDevider deviderSize="24" />
    <div class="header__area-bottom flex-between">
      <div class="area-bottom__buttons">
        <div
          class="buttons__item"
          v-for="button in bottomAreaButtons"
          :key="button.id"
        >
          <Button v-bind:iconName="button.iconName" v-bind:text="button.text" />
        </div>
      </div>
      <Button
        class="buttton__item-ellepsis"
        iconName="VerticalEllepsis"
        type="text"
        text=""
      />
    </div>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
import Button from "@/components/elements/Button";
export default {
  data() {
    return {
      status: "Открыта",
      isHard: true,
      middleAreaButtons: [
        {
          id: 1,
          iconName: "Location",
          type: "text",
          text: "Москва",
        },
        {
          id: 2,
          iconName: "User-light",
          type: "text",
          text: "5",
        },
        {
          id: 3,
          iconName: "Work",
          type: "text",
          text: "Новый (ВТБ МСБ)",
        },
        {
          id: 4,
          iconName: "RemoteWork",
          type: "text",
          text: "Можно на удаленку",
        },
      ],
      bottomAreaButtons: [
        {
          id: 1,
          iconName: "OpenPositions",
          text: "Открыть позиции",
        },
        {
          id: 2,
          iconName: "CancelPositions",
          text: "Отменить позиции",
        },
      ],
      options: [
        {
          value: "Открыта",
          label: "Открыта",
        },
        {
          value: "Закрыта",
          label: "Закрыта",
        },
      ],
      vacancyName: "Ведущий специалист по тестированию",
    };
  },
  name: "vacancy-header",
  components: { VacancyDevider, Button },
};
</script>

<style scoped>
.area-middle__item {
  margin-right: 35px;
}
.area-bottom__buttons,
.header__area-top,
.header__area-middle,
.header__area-bottom {
  display: flex;
  flex-direction: row;
}
.buttons__item {
  margin-right: 15px;
}
.buttton__item-ellepsis {
  padding-top: 7px;
}
.flex-between {
  justify-content: space-between;
}
.header__title {
  font-family: Arial;
  font-weight: 400;
  font-size: 40px;
  margin: 0px;
  line-height: 48px;
}
.el-input__inner {
  border-radius: 10px;
  color: black;
  height: 32px;
  width: 126px;
}
.el-tag {
  border-radius: 12px;
  font-family: Arial;
  font-weight: 400;
  font-size: 16px;
  padding: 0px 10px;
}
.el-button {
  background: #eff8ff;
  border-radius: 12px;
  border-color: white;
}
.el-button--primary {
  color: #2d81ce;
  font-weight: bold;
}
.el-button--text {
  background-color: transparent;
  border-color: transparent;
}
.vacancy-header {
  display: flex;
  flex-direction: column;
}
</style>