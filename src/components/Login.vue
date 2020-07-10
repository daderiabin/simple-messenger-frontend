<template>
  <v-form>
    <v-container>
      <v-card>
        <v-toolbar dark>
          <v-toolbar-title>
            Log In
          </v-toolbar-title>
        </v-toolbar>

        <v-row align="center" justify="center">
          <v-col cols="10" md="9">
            <v-text-field
              v-model="userName"
              class="mr-4"
              label="User Name"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="10" md="9">
            <v-text-field
              v-model="password"
              class="mr-4"
              label="Password"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="10" md="9">
            <v-btn class="mr-4" @click="login">log in</v-btn>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
  </v-form>
</template>

<script>
import axios from "axios";

export default {
  name: "Register",
  data() {
    return {
      userName: "",
      password: "",
    };
  },
  methods: {
    async login() {
      this.$store.dispatch("login", {
        userName: this.userName,
        password: this.password,
      });
    },
  },
};
</script>
