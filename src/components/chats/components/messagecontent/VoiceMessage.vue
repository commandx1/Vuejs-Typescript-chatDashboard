<template>
  <div v-if="messageContent.type">
    <i class="fas fa-microphone"></i>
    {{ voiceMessageDuration(messageContent.duration) }}
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: { messageContent: Object },
  methods: {
    voiceMessageDuration(duration: number) {
      const newDuration: string = duration.toString();
      let minute = newDuration.substring(0, newDuration.lastIndexOf("."));
      minute = Number(minute) > 9 ? minute : "0" + minute;
      let second = newDuration.substring(newDuration.lastIndexOf(".") + 1);
      second = Number(second) > 9 ? second : "0" + second;
      return "Voice message (" + minute + ":" + second + ")";
    },
  },
});
</script>