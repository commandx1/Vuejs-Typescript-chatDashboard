<template>
  <div class="content mt-4 d-flex">
    <div class="w-90">
      <VoiceMessage
        :messageContent="user.messages[user.messages.length - 1].content"
      />
      {{ user.messages[user.messages.length - 1].content.text }}
      <div class="d-flex mt-2">
        <Files
          :type="'file'"
          :content="user.messages[user.messages.length - 1].content"
        />
        <Files
          :type="'image'"
          :content="user.messages[user.messages.length - 1].content"
        />
      </div>
    </div>
    <UnreadMessagesCount :messages="user.messages" />
  </div>
</template>


<script lang="ts">
import Vue from "vue";
import FilesVue from "./Files.vue";
import UnreadMessagesCountVue from "./UnreadMessagesCount.vue";
import VoiceMessageVue from "./VoiceMessage.vue";
export default Vue.extend({
  props: {
    user: Object,
  },
  components: {
    VoiceMessage: VoiceMessageVue,
    Files: FilesVue,
    UnreadMessagesCount: UnreadMessagesCountVue,
  },
});
</script>