<template>
  <div class="vacancy-header">
    <div class="area-top flex-between">
      <div class="header__tags">
        <Tag text="Сложная вакансия" disabled />
      </div>
      <DropDown />
    </div>
    <VacancyDevider deviderSize="40" />
    <h1 class="header__title">{{ vacancyName }}</h1>
    <VacancyDevider deviderSize="24" />
    <div class="area-middle">
      <div class="area-middle__item">
        <Icon iconName="Location" iconColor="#2d81ce" />
        <p class="text blue">Москва</p>
      </div>
      <div class="area-middle__item">
        <Icon iconName="User-light" iconColor="#2d81ce" />
        <p class="text blue">5</p>
      </div>
      <div class="area-middle__item">
        <Icon iconName="Work" iconColor="#2d81ce" />
        <p class="text blue">Новый (ВТБ МСБ)</p>
      </div>
      <div class="area-middle__item">
        <Icon iconName="RemoteWork" iconColor="#2d81ce" />
        <p class="text blue">Можно на удаленку</p>
      </div>
    </div>
    <VacancyDevider deviderSize="24" />
    <div class="area-bottom flex-between">
      <div>
        <Button
          buttonSize="big"
          buttonColor="blue"
          buttonText="Открыть позиции"
          hasLeftIcon
          iconName="OpenPositions"
        />
        <Button
          buttonSize="big"
          buttonColor="blue"
          buttonText="Отменить позиции"
          hasLeftIcon
          iconName="CancelPositions"
        />
      </div>
      <Button
        class="buttons__ellepsis"
        buttonSize="big"
        buttonColor="transparent"
        buttonText=""
        hasRightIcon
        iconName="VerticalEllepsis"
      />
    </div>
  </div>
</template>

<script>
import VacancyDevider from "@/components/elements/VacancyDevider";
import Button from "../../elements/Button";
import Tag from "@/components/elements/Tag";
import Icon from "@/components/elements/Icon";
import DropDown from "@/components/elements/DropDown";
export default {
  name: "vacancy-header",
  components: { VacancyDevider, Button, Tag, Icon, DropDown },
  data() {
    return {
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
};
</script>

<style lang="scss" scoped>
.area {
  &-middle__item {
    display: flex;
    flex-direction: row;
    margin-top: 10px;
    margin-right: 35px;
  }
  &-bottom {
    display: flex;
    flex-direction: row;
    flex-flow: row wrap;
  }
  &-top,
  &-middle {
    display: flex;
    flex-direction: row;
    flex-flow: row wrap;
    margin-top: -10px;
  }
}

.blue {
  color: $blue-600;
}

.buttons__ellepsis {
  padding: 0px;
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

.el {
  &-tag {
    border-radius: 12px;
    font-family: Arial;
    font-weight: 400;
    font-size: 16px;
    padding: 0px 10px;
  }
  &-button {
    border-radius: 12px;
    border-color: $white;
    &--primary {
      color: #2d81ce;
      font-weight: bold;
    }
    &--text {
      background-color: transparent;
      border-color: transparent;
    }
  }
}

.vacancy-header {
  display: flex;
  flex-direction: column;
}

.text {
  margin: 0px;
  align-self: center;
  font-size: 16px;
  margin: 2px 5px 0px 5px;
}
</style>