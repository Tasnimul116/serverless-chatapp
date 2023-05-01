<script setup>
 import AuthPage from "./AuthPage/index.vue";
 import ChatPage from "./Chatpage/index.vue";

</script>

<template>
  <AuthPage v-if="!user" @onAuth="handleAuth"/>
  <ChatPage v-else v-bind:username="user.username"
  v-bind:secret="user.secret"/>
</template>


<script>
export default {
  data() {
    return {
      user: undefined,
    };
  },

  methods: {
    handleAuth(user) {
      this.user = user;
    },
  },
};
</script>
