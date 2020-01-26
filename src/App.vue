<template>
  <v-app>

    <!-- Navbar -->
    <v-app-bar app dark color="primary">
      <v-toolbar-title>Vuetify Dashboard</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text rounded>Home</v-btn>
      <v-btn text rounded>Login</v-btn>
    </v-app-bar>

    <!-- content -->
    <v-content>
      <Login />
    </v-content>

    <!-- footer -->
    <v-footer
      color="primary lighten-1"
      padless
    >
      <v-row
        justify="center"
        no-gutters
      >
        <v-btn
          v-for="link in links"
          :key="link"
          color="white"
          text
          rounded
          class="my-2"
        >
          {{ link }}
        </v-btn>
        <v-col
          class="primary lighten-2 py-4 text-center white--text"
          cols="12"
        >
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
import Login from './components/Login'

export default {
  name: 'App',

  components: {
    Login
  },

  data: () => ({
    links: [
      'Home',
      'Login'
    ]
  }),
};
</script>
