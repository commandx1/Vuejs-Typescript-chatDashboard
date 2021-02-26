<template>
  <div class="messages">
    <div class="messagecontent py-3 px-5">
      <div
        v-for="msg in user.messages"
        :class="{ user: msg.user !== 'You' }"
        :key="msg.id"
        class="message d-flex align-items-center"
      >
        <Avatar :msg="msg" :user="user" />
        <div class="d-flex align-items-end flex-column messagecontentwrapper">
          <div class="msgcontent p-3">
            <MessageText :msg="msg" />
            <Files :msg="msg" :type="'file'" />
            <Files :msg="msg" :type="'image'" />
          </div>
          <span class="date"> {{ msg.date }}</span>
        </div>
        <i class="fas fa-ellipsis-h"></i>
        <img
          src="https://static.thenounproject.com/png/1003313-200.png"
          alt="checked"
          v-if="msg.user === 'You'"
        />
      </div>
    </div>
  </div>
</template>


<script lang="ts">
import AvatarVue from "../../../Avatar.vue";
import Vue from "vue";
import MessageTextVue from "./components/MessageText.vue";
import FilesVue from "./components/Files.vue";
export default Vue.extend({
  props: { user: Object },
  components: {
    Avatar: AvatarVue,
    MessageText: MessageTextVue,
    Files: FilesVue,
  },
});
</script>