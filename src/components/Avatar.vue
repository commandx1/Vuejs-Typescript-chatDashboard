<template>
  <div class="chats">
    <div v-if="msg.user !== 'You'" class="image">
      <img :src="user.imgUrl" alt="" />
    </div>
  </div>
</template>
<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    msg: Object,
    user: Object,
  },
});
</script>