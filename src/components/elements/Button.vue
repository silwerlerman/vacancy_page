<template>
  <!-- Новый компонент, сейчас используется для всех кнопок -->
  <el-button
    :class="{
      blueButton: buttonColor === 'blue',
      darkBlueButton: buttonColor === 'darkBlue',
      transparentButton: buttonColor === 'transparent',
      big: buttonSize === 'big',
      medium: buttonSize === 'medium',
      small: buttonSize === 'small',
    }"
    :disabled="disabled"
    @click="click"
  >
    <div class="button__content">
      <Icon
        v-if="hasLeftIcon"
        :icon-name="iconName"
        :icon-color="contentColor"
      />
      <p
        v-if="buttonText !== ''"
        class="content__text"
        :style="{ color: contentColor }"
      >
        {{ buttonText }}
      </p>
      <Icon
        v-if="hasRightIcon"
        :icon-name="iconName"
        :icon-color="contentColor"
      />
    </div>
  </el-button>
</template>
<script>
import Icon from "@/components/elements/Icon";
export default {
  name: "Button",
  components: {
    Icon,
  },
  props: {
    buttonSize: {
      type: String,
      default: "medium",
    },
    buttonColor: {
      type: String,
      default: "blue",
    },
    buttonText: {
      type: String,
      default: "Текст",
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    hasLeftIcon: {
      type: Boolean,
      default: false,
    },
    hasRightIcon: {
      type: Boolean,
      default: false,
    },
    iconName: {
      type: String,
      default: "User-bold",
    },
    click: {
      type: Function,
      default: () => {
        console.log("Нажата кнопка!");
      },
    },
  },
  computed: {
    contentColor: function () {
      if (this.buttonColor === "darkBlue") {
        return this.disabled ? "#9E9E9E" : "#FFFFFF";
      } else if (this.buttonColor === "blue") {
        return this.disabled ? "#9E9E9E" : "#2D81CE";
      } else if (this.buttonColor === "transparent") {
        return this.disabled ? "transparent" : "transparent";
      } else return "#FFFFFF";
    },
  },
};
</script>
<style lang="scss" scoped>
.el-button {
  border-radius: 12px;
  padding-top: 7px;
  &.medium {
    border-radius: 12px;
    padding-top: 2px;
  }
  &.small {
    border-radius: 12px;
    padding-top: 0px;
  }
}

.big {
  height: 40px;
}

.medium {
  height: 30px;
}

.small {
  height: 25px;
  padding-top: 5px;
}

.blueButton {
  background: $blue-100;
  &:hover {
    background: $blue-200;
    color: $blue-700;
  }
  &:disabled {
    background: $black-100;
  }
}

.darkBlueButton {
  background: $blue-600;
  &:hover {
    background: $blue-700;
  }
  &:disabled {
    background: $black-300;
  }
}

.transparentButton {
  background: transparent;
  border-color: transparent;
  &:hover {
    background: transparent;
    border-color: transparent;
    background: $blue-100;
  }
}

.button__content {
  display: flex;
  flex-direction: row;
  justify-content: center;
  &-icon {
    padding-bottom: 2px;
  }
}

.content__text {
  font-weight: bold;
  font-size: 16px;
  margin: 5px;
}
</style>