<template>
  <div :class="classes" class="paper">
    <slot></slot>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  props: {
    classes: String,
  },
});
</script>

<style scoped lang="scss">
div.paper {
  border-radius: 0.25rem;
  background: white;
  width: 100%;
  box-shadow: 0 1.5px 2px #e5e5e5, 0 1.8px 2px #e5e5e5, 0 2px 2px #e5e5e5;
}
</style>
