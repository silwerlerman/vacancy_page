<template>
  <div class="dropdown">
    <el-select v-model="status" plain size="small">
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value"
      >
        <span class="dropdown__option">{{ item.value }}</span>
      </el-option>
    </el-select>
  </div>
</template>

<script>
export default {
  name: "Dropdown",
  data() {
    return {
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
      status: "Открыта",
    };
  },
};
</script>

<style lang="scss" scoped>
.el-select {
  max-width: 125px;
  & ::v-deep .el-select__caret.is-reverse {
    transform: rotateZ(180deg);
  }
  & ::v-deep .el-select__caret {
    transform: rotateZ(0deg);
  }
  & ::v-deep .el-input__inner {
    border-radius: 10px;
    font-size: 14px;
    font-family: Arial, sans-serif;
  }
  & ::v-deep .el-icon-arrow-up::before {
    content: url("arrow.svg");
  }
  & ::v-deep .el-input__icon {
    line-height: 20px;
    padding-bottom: 2px;
  }
}

.dropdown__option {
  font-family: Arial, sans-serif;
}
</style>