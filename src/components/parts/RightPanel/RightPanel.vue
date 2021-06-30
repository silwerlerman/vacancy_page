<template>
  <div class="right-panel">
    <PanelTabBar />
    <div class="right-panel__content">
      <PanelProgressBar candidates="3" maxCandidates="11" />
    </div>
    <div class="content__center">
      <StagePanel
        v-for="(item, index) in stages"
        :key="index"
        :title="item.label"
        :candidateCount="item.candidates"
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
  name: "right-panel",
  components: { PanelTabBar, PanelProgressBar, StagePanel, Button },
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
          label: "Первичное интервью с рекрутером",
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
          label: "Назначено интервью с внут. зак.",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 7,
          label: "Проведено интервью с внут. зак.",
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
          label: "Назначено интервью с внеш. зак.",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 10,
          label: "Проведено интервью с внеш. зак.",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 11,
          label: "Оффер",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 12,
          label: "Служба безопасности",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 13,
          label: "Подготовка к выходу",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 14,
          label: "Принят",
          candidates: "0",
          update: "29.05.2021",
        },
        {
          id: 14,
          label: "Отказ",
          candidates: "0",
          update: "29.05.2021",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.right-panel {
  background: $white;
  border-radius: 12px;
  margin: 20px 0px;
  min-width: 385px;
  word-wrap: break-word;
  position: fixed;
  margin-left: 15px;
}

.content__center {
  overflow-y: auto;
  max-height: 416px;
  -ms-overflow-style: none;
  &::-webkit-scrollbar {
    width: 0;
  }
}

.content__footer {
  padding: 25px;
  border-top: 1px solid $black-200;
  align-items: stretch;
  flex-direction: column;
  display: flex;
}
</style>