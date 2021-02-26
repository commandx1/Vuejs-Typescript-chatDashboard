<template>
  <div class="userinfo d-flex">
    <div class="image">
      <span v-if="user.isOnline" class="online"></span>
      <img class="border" :src="user.imgUrl" alt="" />
    </div>
    <div class="d-flex flex-column">
      <span class="username">{{ user.name }}</span>
      <span class="status">{{
        user.messages[0].content.type && user.isOnline
          ? "records voice message"
          : !user.messages[0].content.type && user.isOnline
          ? "writes"
          : "last online " + user.lastOnline
      }}</span>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    user: Object,
  },
});
</script>