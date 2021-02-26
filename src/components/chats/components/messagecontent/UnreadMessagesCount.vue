<template>
  <div class="w-10">
    <div
      v-if="countOfUnreadMessages(messages) > 0"
      class="circle d-flex align-items-center justify-content-center"
    >
      {{ countOfUnreadMessages(messages) }}
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    messages: Array,
  },
  methods: {
    countOfUnreadMessages(messages: []): number {
      return messages.filter((msg: any) => !msg.hasRead).length;
    },
  },
});
</script>