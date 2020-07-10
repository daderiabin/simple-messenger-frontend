<template>
  <v-form>
    <v-container>
      <v-card>
        <v-toolbar dark>
          <v-toolbar-title>
            New Message
          </v-toolbar-title>
        </v-toolbar>

        <v-row align="center" justify="center">
          <v-col cols="10" md="9">
            <v-text-field
              v-model="messageBody"
              class="mr-4"
              label="Message"
              required
            ></v-text-field>
          </v-col>
          <v-col cols="10" md="2">
            <v-btn class="mr-4" @click="submit">submit</v-btn>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
  </v-form>
</template>

<script>
import axios from "axios";

export default {
  name: "Messages",
  data() {
    return {
      messageBody: "",
    };
  },
  methods: {
    async submit() {
      try {
        this.$store.dispatch('newMessage', this.messageBody);
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>
