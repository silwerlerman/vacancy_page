<template>
  <div class="right-panel__card" @click="click">
    <div class="card__items">
      <p class="items-title">{{ title }}</p>
      <div class="card__bottom">
        <div class="bottom__text">
          <Icon iconName="User-light" iconColor="#2d81ce" />
          <p class="text blue">{{ candidateText }}</p>
        </div>
        <p class="bottom-data">{{ date }}</p>
      </div>
    </div>
  </div>
</template>
<script>
import Icon from "@/components/elements/Icon";
export default {
  props: {
    title: {
      type: String,
      default: "Новый раздел",
    },
    date: {
      type: String,
      default: "29.05.2021",
    },
    candidateCount: {
      type: String,
      default: "0",
    },
  },
  name: "panel-card",
  methods: {
    click: function () {
      console.log("!");
    },
  },
  components: { Icon },
  computed: {
    candidateText: function () {
      if (
        parseInt(this.candidateCount) % 10 === 0 ||
        parseInt(this.candidateCount) % 10 > 5
      )
        return this.candidateCount + " кандидатов";
      else if (parseInt(this.candidateCount) % 10 === 1)
        return this.candidateCount + " кандидат";
      else return this.candidateCount + " кандидата";
    },
  },
};
</script>

<style scoped>
.right-panel__card {
  margin: 10px;
  border: 1px solid #ececec;
  border-radius: 10px;
  background: #fcfcfc;
  padding: 15px;
}
.items-title {
  margin: 0px;
  font-size: 14px;
  font-weight: bold;
  margin-bottom: 10px;
  max-width: 310px;
  line-height: 20px;
}
.card__items {
  justify-content: space-between;
}
.card__bottom {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.button__content-text {
  margin: 0px;
}
.bottom-data {
  margin: 0px;
  align-self: center;
  font-size: 14px;
  color: #c0c0c0;
}
.bottom__text {
  display: flex;
  flex-direction: row;
}
.card__bottom-button {
  margin-left: -4px;
  margin-bottom: -5px;
}
.el-card__body {
  padding: 10px;
}
.text {
  margin: 0px;
  align-self: center;
  font-size: 14px;
  margin: 2px 5px 0px 5px;
}
.blue {
  color: #2d81ce;
}
</style>