<template>
  <div class="row mx-0 h-100">
    <div class="col-2 h-100 border" :class="{ show: openMenu }">
      <SideMenu />
    </div>

    <div class="col border h-100 position-relative">
      <IconButton
        class="position-absolute openMenuButton"
        :class="{ open: openMenu }"
        @clickedToIcon="openMenu = !openMenu"
        ><i class="fas fa-chevron-left"></i
      ></IconButton>
      <Chats @child="test($event)" />
    </div>
    <div class="col border h-100">
      <CurrentChat :user="activeMsgPage" :ready="ready" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import ChatsVue from "./chats/Chats.vue";
import CurrentChatVue from "./currentchat/CurrentChat.vue";
import IconButtonVue from "./IconButton.vue";
import sidemenuVue from "./sidemenu/sidemenu.vue";

export default Vue.extend({
  components: {
    SideMenu: sidemenuVue,
    Chats: ChatsVue,
    CurrentChat: CurrentChatVue,
    IconButton: IconButtonVue,
  },
  data() {
    return {
      openMenu: true,
      ready: false,
      usersFetched: [] as object,
      isLoading: false as boolean, //for fetching data
      activeMsgPage: {},
    };
  },
  methods: {
    test(a: any) {
      this.activeMsgPage = a[0];
      this.ready = true;
    },
  },

  mounted() {
    //Bu verileri kullanmadım; çünkü mockapide mesajların özelliklerini herkese istediğim şekilde verebilmek mümkün değildi. Sadece verileri çekip arrayime atmak amacıyla buraya yazdım.
    this.isLoading = true;
    fetch("https://6037994a5435040017722cef.mockapi.io/api/v1/users")
      .then((res) => res.json())
      .then((data) => {
        this.usersFetched = data;
        this.isLoading = false;
      })
      .catch((err) => {
        console.log(err);
        this.isLoading = false;
      });
  },
});
</script>

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
