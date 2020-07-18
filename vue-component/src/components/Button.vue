<template>
  <button class="button" type="button" @click="click()">
    <slot>{{ text }}</slot>
  </button>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class Button extends Vue {
  @Prop({ type: String, required: true }) readonly text!: string;

  click() {
    this.$emit("click");
  }
}
</script>

<style scoped>
.button {
  border-color: black;
}
</style>
