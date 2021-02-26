<template >
  <div v-if="msg.content.text">
    {{ msg.content.text }}
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: { msg: Object },
});
</script>