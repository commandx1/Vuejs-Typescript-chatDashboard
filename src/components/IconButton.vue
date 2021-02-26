<template>
  <div
    @click="clickedToIconButton"
    :class="classes"
    class="iconbutton d-flex align-items-center justify-content-center pointer"
  >
    <slot></slot>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    classes: String,
  },
  methods: {
    clickedToIconButton() {
      this.$emit("clickedToIcon");
    },
  },
});
</script>

