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
  name: "panel-card",
  components: { Icon },
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
  methods: {
    click: function () {
      console.log("!");
    },
  },
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

<style lang="scss" scoped>
.right-panel__card {
  margin: 10px;
  border: 1px solid $black-200;
  border-radius: 10px;
  background: $black-100;
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

.card {
  &__items {
    justify-content: space-between;
  }
  &__bottom {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    &-button {
      margin-left: -4px;
      margin-bottom: -5px;
    }
  }
}

.button__content-text {
  margin: 0px;
}

.bottom {
  &-data {
    margin: 0px;
    align-self: center;
    font-size: 14px;
    color: $black-400;
  }
  &__text {
    display: flex;
    flex-direction: row;
  }
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
  color: $blue-600;
}
</style>