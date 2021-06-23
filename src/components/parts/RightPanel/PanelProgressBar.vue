<template>
  <div class="panel-progress-bar">
    <div class="progress-bar__title flex-row">
      <p class="title__text">Прогресс закрытия вакансии</p>
      <div class="title__counter flex-row">
        <Icon iconName="User-bold" iconColor="#2D81CE" />
        <p class="text blue">{{ candidates }}/{{ maxCandidates }}</p>
      </div>
    </div>
    <div>
      <el-progress
        :stroke-width="12"
        :percentage="percentage"
        :color="'#40BF2B'"
        :show-text="false"
      ></el-progress>
    </div>
  </div>
</template>
<script>
import Icon from "@/components/elements/Icon";
export default {
  props: {
    candidates: {
      type: String,
      default: "0",
    },
    maxCandidates: {
      type: String,
      default: "0",
    },
  },
  data() {
    return {
      customColors: [
        { color: "#f56c6c", percentage: 20 },
        {
          color:
            "linear-gradient(90deg, #1f005c, #5b0060, #870160, #ac255e, #ca485c, #e16b5c, #f39060, #ffb56b)",
          percentage: 40,
        },
        { color: "#5cb87a", percentage: 60 },
        { color: "#1989fa", percentage: 80 },
        { color: "#6f7ad3", percentage: 100 },
      ],
    };
  },
  methods: {},
  components: { Icon },
  computed: {
    percentage: function () {
      return (parseInt(this.candidates) / parseInt(this.maxCandidates)) * 100;
    },
  },
};
</script>
<style scoped>
.panel-progress-bar {
  padding: 25px;
  border-bottom: 1px solid #ececec;
}
.flex-row {
  display: flex;
  flex-direction: row;
}
.progress-bar__title {
  margin: 0px 0px 15px 0px;
}
.title__indicator {
  align-self: center;
  margin-left: 20px;
}
.title__text {
  color: #378bd8;
  font-weight: bold;
  margin: 0px;
  margin-right: 20px;
  align-self: center;
}
.el-progress-bar__inner {
  border-radius: 4px;
  background-color: linear-gradient(90deg, #67e453 0%, #1f8235 129.17%);
}
.text {
  margin: 0px;
  margin-left: 5px;
  align-self: center;
  font-size: 16px;
  font-weight: bold;
}
.blue {
  color: #2d81ce;
}
</style>