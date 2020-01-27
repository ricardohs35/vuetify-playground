<template>
  <v-app>

    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>


    <!-- Navbar -->
    <v-app-bar app dark color="primary">
      <v-toolbar-title>Vuetify Dashboard</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        v-for="link in links"
        :key="`${link.label}-header-link`"
        :to="link.to"
        text
        rounded
      >{{ link.label }}</v-btn>
    </v-app-bar>

    <!-- content -->
    <v-content>
      <router-view/>
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
          :to="link.to"
          :key="`${link.label}-footer-link`"
          color="white"
          text
          rounded
          class="my-2"
        >
          {{ link.label }}
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
export default {
  name: 'App',

  data: () => ({
    links: [
      {
        label: 'Home',
        to: '/'
      },
      {
        label: 'Login',
        to: '/login'
      }
    ]
  }),
};
</script>
