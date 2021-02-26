<template>
  <div class="chat p-5 h-100">
    <Paper :classes="'h-100'" v-if="ready">
      <div class="header chats d-flex align-items-center px-5 border-bottom">
        <UserInfo :user="user" />
        <div style="flex: 1"></div>
        <IconButton v-for="icon in icons" :key="icon" v-html="icon" />
      </div>
      <Messages :user="user" />
      <MessageTextArea />
    </Paper>
    <Paper :classes="'p-5'" v-else>
      Mesajlarınızı görmek için bir tanesini seçin.
    </Paper>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import UserInfoVue from "../chats/components/UserInfo.vue";
import PaperVue from "../Paper.vue";
import MessageAreaVue from "./components/MessageArea.vue";
import IconButtonVue from "../IconButton.vue";
import MessagesVue from "./components/Messages/Messages.vue";
import "./currentchat.scss";

export default Vue.extend({
  props: {
    user: Object,
    ready: Boolean,
  },
  data() {
    return {
      icons: [
        '<i class="fas fa-paperclip"></i>',
        '<i class="fas fa-ellipsis-v"></i>',
      ],
    };
  },
  components: {
    Paper: PaperVue,
    MessageTextArea: MessageAreaVue,
    UserInfo: UserInfoVue,
    IconButton: IconButtonVue,
    Messages: MessagesVue,
  },
});
</script>

<style scoped lang="scss">
</style>
