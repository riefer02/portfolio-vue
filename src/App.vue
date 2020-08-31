<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <v-list dense>
        <v-list-item
          link
          v-for="item in items"
          :key="item.text"
          :to="item.route"
        >
          <v-list-item-action>
            <v-icon>mdi-{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ item.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app color="indigo" dark>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>riefer.io</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <transition name="fade">
        <router-view />
      </transition>
    </v-main>
    <v-footer color="indigo" app>
      <span class="white--text">&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},
  props: {
    source: String,
  },
  data: () => ({
    drawer: null,
    items: [
      {
        icon: "home",
        text: "Home",
        route: "/",
      },
      {
        icon: "book-open-page-variant",
        text: "Biography",
        route: "/biography",
      },
      {
        icon: "test-tube",
        text: "Resume",
        route: "/resume",
      },
      {
        icon: "database",
        text: "Hobbies",
        route: "/hobbies",
      },
    ],
  }),
};
</script>
