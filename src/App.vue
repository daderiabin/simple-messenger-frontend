<template>
  <v-app>
    <v-app-bar app>
      <v-btn class="ma-2" outlined to="/">Messages</v-btn>
      <v-btn class="ma-2" outlined to="/new-msg">New Message</v-btn>
      <v-spacer/>
      <v-btn class="ma-2" v-if="!$store.state.token" outlined to="/register">Sign Up</v-btn>
      <v-btn class="ma-2" v-if="!$store.state.token" outlined to="/login">Log In</v-btn>
      <v-btn class="ma-2" v-if="$store.state.token" @click="$store.commit('logout')" outlined>Log Out</v-btn>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>

</template>

<script>
import Messages from './components/Messages.vue';
import NewMessage from './components/NewMessage.vue';

export default {
  name: 'App',

  components: {
    Messages,
    NewMessage
  },

  data: () => {
    return {
    }
  }
};
</script>
