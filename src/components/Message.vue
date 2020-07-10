<template>
    <v-container>
      <v-card>
        <v-toolbar dark>
          <v-toolbar-title>
            Message
          </v-toolbar-title>
        </v-toolbar>

        <v-row align="center" justify="center">
          <v-col cols="10" md="2">
            <v-card-text>
              {{message.text}}
            </v-card-text>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
</template>

<script>
import axios from "axios";

export default {
  name: "Messages",
  data() {
    return {
      message: "",
    };
  },

  async created() {
    this.message = (await this.$store.dispatch('getMessage', this.$route.params.id)).data;
  }
};
</script>
