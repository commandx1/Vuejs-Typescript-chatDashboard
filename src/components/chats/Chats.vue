<template>
  <div class="p-5 chats h-100">
    <div style="height: 150px">
      <Header />
      <Searchbox />
    </div>

    <div style="height: calc(100% - 150px); overflow-y: auto">
      <Paper v-for="user in users" :class="'my-3'" :key="user.id">
        <div
          @click="clicked(user.id)"
          class="p-4 pointer"
          :class="{ active: user.clicked }"
        >
          <div class="d-flex justify-content-between">
            <UserInfo :user="user" />
            <LastMessageTime
              :date="user.messages[user.messages.length - 1].date"
            />
          </div>
          <MessageContentWrapper :user="user" />
        </div>
      </Paper>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import PaperVue from "../Paper.vue";
import HeaderVue from "./components/Header.vue";
import LastMessageTimeVue from "./components/LastMessageTime.vue";
import SearchboxVue from "./components/Searchbox.vue";
import UserInfoVue from "./components/UserInfo.vue";
import "./chats.scss";
import MessageContentWrapperVue from "./components/messagecontent/MessageContentWrapper.vue";

export default Vue.extend({
  components: {
    Paper: PaperVue,
    Header: HeaderVue,
    Searchbox: SearchboxVue,
    UserInfo: UserInfoVue,
    LastMessageTime: LastMessageTimeVue,
    MessageContentWrapper: MessageContentWrapperVue,
  },
  data() {
    return {
      users: [
        {
          id: Math.random(),
          name: "El Capitán",
          isOnline: true,
          imgUrl:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTKC3rDFX9_xfrRQUq-CNx0lonAjS-rwmnIKw&usqp=CAU",
          messages: [
            {
              id: Math.random(),
              user: "You",
              hasRead: true,
              date: "6 minutes ago", //Herbirisi için uygun tarih ayarlamak yerine bu şekilde dakika temsil eden yer tutucu olsun dedim
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "You",
              hasRead: true,
              date: "5 minutes ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "Sergio",
              hasRead: false,
              date: "5 minutes ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "Sergio",
              hasRead: false,
              date: "4 minutes ago",
              type: "text",
              content: {
                text:
                  "En yeni mesaj. Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
          ],
        },
        {
          id: Math.random(),
          name: "Karim Benzema",
          isOnline: true,
          imgUrl:
            "https://yanginhaber.com/wp-content/uploads/2021/01/karim-benzema-real-madrid-2019-20_b7t0741hb50d1lcnbogjzbmbt.jpg",
          messages: [
            {
              id: Math.random(),
              user: "Karim",
              hasRead: true,
              date: "4 minutes ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "Karim",
              hasRead: false,
              date: "2 minutes ago",
              content: {
                type: "voice",
                duration: 1.15,
                files: [
                  { name: "blablabla.docs", size: "40.05" },
                  { name: "blabla.pdf", size: "42.25" },
                ],
                images: [{ name: "image.jpeg", size: "80" }],
              },
            },
          ],
        },
        {
          id: Math.random(),
          name: "Toni Kroos",
          isOnline: false,
          lastOnline: "5 hours ago",
          imgUrl:
            "https://pbs.twimg.com/profile_images/1144875187508338688/0MtdI4-f_400x400.jpg",
          messages: [
            {
              id: Math.random(),
              user: "You",
              hasRead: true,
              date: "3 days ago",
              content: {
                files: [
                  {
                    name: "NEW_Style.zip",
                    size: "52.05",
                  },
                ],
                text:
                  "On the Boundaries of Goods and Evils; finibus may also be translated as purposes.",
              },
            },
            {
              id: Math.random(),
              user: "Toni",
              hasRead: true,
              date: "4 days ago",
              content: {
                files: [
                  {
                    name: "Style.zip",
                    size: "41.36",
                  },
                ],
                text:
                  "On the Boundaries of Goods and Evils; finibus may also be translated as purposes.",
              },
            },
            {
              id: Math.random(),
              user: "You",
              hasRead: true,
              date: "4 days ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "Toni",
              hasRead: true,
              date: "4 days ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "You",
              hasRead: true,
              date: "4 days ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "Toni",
              hasRead: true,
              date: "4 days ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "You",
              hasRead: true,
              date: "4 days ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "Toni",
              hasRead: true,
              date: "4 days ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "You",
              hasRead: true,
              date: "4 days ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
            {
              id: Math.random(),
              user: "Toni",
              hasRead: true,
              date: "4 days ago",
              content: {
                text:
                  "Most of its text is made up from sections 1.10.32–3 of Cicero's De finibus bonorum et malorum (On the Boundaries of Goods and Evils; finibus may also be translated as purposes).",
              },
            },
          ].reverse(),
        },
      ],
    };
  },
  methods: {
    clicked(id: string) {
      const updatedUsers = this.users.map((user: any) =>
        user.id === id
          ? { ...user, clicked: true }
          : { ...user, clicked: false }
      );
      this.users = updatedUsers;
      this.$emit(
        "child",
        this.users.filter((u: any) => u.id === id)
      );
    },
  },
});
</script>
