<template>
  <v-container>
    <v-card>
      <v-toolbar dark>
        <v-toolbar-title>
          Messages
        </v-toolbar-title>
      </v-toolbar>

      <v-row align="center" justify="center">
        <v-col cols="12" md="12">
          <v-list>
            <v-list-item v-for="(message, i) in $store.state.messages" :key="i" :to="`msg/` + i">
              <v-list-item-content>
                <v-list-item-title v-text="message.user"></v-list-item-title>
                <v-list-item-subtitle v-text="message.text"></v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<script>

export default {
  name: "Messages",
  async created() {
    this.$store.dispatch('getMessages');
  },
};
</script>
