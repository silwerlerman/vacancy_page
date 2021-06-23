<template>
  <div class="right-panel">
    <PanelTabBar />
    <div class="right-panel__content">
      <PanelProgressBar />
    </div>
    <div class="content__center">
      <StagePanel
        v-for="(item, index) in stages"
        :key="index"
        v-bind:title="item.label"
        v-bind:candidateCount="item.candidates"
      />
    </div>
    <div class="content__footer">
      <Button
        buttonSize="big"
        buttonColor="darkBlue"
        buttonText="Прикрепить кандидата"
      />
    </div>
  </div>
</template>

<script>
import PanelTabBar from "./PanelTabBar";
import PanelProgressBar from "./PanelProgressBar";
import StagePanel from "./StagePanel";
import Button from "../../elements/Button";
export default {
  data() {
    return {
      stages: [
        {
          id: 1,
          label: "Добавлен",
          candidates: "4",
          update: "29.05.2021",
        },
        {
          id: 2,
          label: "Телефонное интервью",
          candidates: "1",
          update: "29.05.2021",
        },
        {
          id: 3,
          label: "Назначено интервью с рекрутером",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 4,
          label: "Резюме у заказчика",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 5,
          label: "Тестовое задание",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 6,
          label: "Назначено интервью с внутренним заказчиком",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 7,
          label: "Проведено интервью с внутренним заказчиком",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 8,
          label: "Резюме у внешнего заказчика",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 9,
          label: "Назначено интервью с внешним заказчиком",
          candidates: "0",
          update: "29.05.2021",
        },
      ],
    };
  },
  name: "right-panel",
  components: { PanelTabBar, PanelProgressBar, StagePanel, Button },
};
</script>

<style scoped>
.right-panel {
  background: #ffffff;
  border-radius: 12px;
  margin: 20px 0px;
  min-width: 385px;
  word-wrap: break-word;
  position: fixed;
  margin-left: 15px;
}
.content__center {
  overflow-y: auto;
  max-height: 555px;
  -ms-overflow-style: none;
}
.content__center::-webkit-scrollbar {
  width: 0;
}
.content__footer {
  padding: 25px;
  border-top: 1px solid #ececec;
  align-items: stretch;
  flex-direction: column;
  display: flex;
}
</style>