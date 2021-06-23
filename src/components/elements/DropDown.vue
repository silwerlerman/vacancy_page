<template>
  <div class="dropdown">
    <el-select v-model="value" placeholder="Select">
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value"
      >
      </el-option>
    </el-select>
  </div>
</template>

<script>
export default {
  name: "dropdown",
};
</script>

<style scoped>
.dropdown {
  height: 40px;
}
</style>