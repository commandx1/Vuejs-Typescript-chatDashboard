<template>
  <div class="lastseen">{{ date }}</div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    date: String,
  },
});
</script>