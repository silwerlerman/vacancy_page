<template>
  <div class="messages__items">
    <Button iconName="User-light" type="text" v-bind:text="message.author" />
    <div class="items__arrow">
      <svg
        width="4"
        height="8"
        viewBox="0 0 4 8"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path d="M4 4L0 0V8L4 4Z" fill="#0C0C0C" />
      </svg>
    </div>
    <div v-if="message.type === 'AddCandidate'" class="items__text">
      <p class="text">{{ message.text }}&nbsp;</p>
      <p class="text blue">{{ message.name }}</p>
    </div>
    <div v-else-if="message.type === 'FieldUpdate'" class="items__text">
      <p class="text">{{ message.text }}&nbsp;</p>
      <p class="text blue">{{ message.fieldName }}&nbsp;</p>
      <p class="text">с&nbsp;</p>
      <p class="text blue">{{ message.oldValue }}&nbsp;</p>
      <p class="text">на&nbsp;</p>
      <p class="text blue">{{ message.newValue }}&nbsp;</p>
      <p class="text blue">{{ message.name }}</p>
    </div>
    <div v-else-if="message.type === 'VacancyCreate'" class="items__text">
      <p class="text">{{ message.text }}&nbsp;</p>
      <p class="text blue">{{ message.name }}</p>
    </div>
  </div>
</template>
<script>
import Button from "./Button";
export default {
  props: {
    message: Object,
  },
  components: { Button },
};
</script>
<style scoped>
.messages__items {
  display: flex;
  flex-direction: row;
}
.items__text {
  display: flex;
  flex-direction: row;
  justify-self: center;
}
.items__arrow {
  padding-top: 2px;
  margin: 0px 15px;
}
.text {
  margin: 0px;
  align-self: center;
  font-size: 16px;
}
.blue {
  color: #2d81ce;
}
</style>
