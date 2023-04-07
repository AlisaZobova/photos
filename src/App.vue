<template>
  <v-app>
    <header class="page-header">
      <nav>
        <v-spacer />

        <ul class="menu-links">
          <li
            class="menu-links__item"
            v-for="(item, i) in menuItems"
            :key="i"
            @click="currentPage = item"
          >
            <a
              href="#"
              :class="
                'menu-links__item-url' +
                (currentPage === item ? '--selected' : '')
              "
              >{{ item }}</a
            >
          </li>
        </ul>

        <v-menu offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-app-bar-nav-icon
              class="menu-icon"
              v-bind="attrs"
              v-on="on"
            ></v-app-bar-nav-icon>
          </template>
          <v-list class="menu-list">
            <v-list-item
              class="menu-links__item"
              v-for="(item, i) in menuItems"
              :key="i"
              @click="currentPage = item"
            >
              <v-list-item-title
                ><a
                  href="#"
                  :class="
                    'menu-links__item-url' +
                    (currentPage === item ? '--selected' : '')
                  "
                  >{{ item }}</a
                ></v-list-item-title
              >
            </v-list-item>
          </v-list>
        </v-menu>

        <ul class="menu-icons">
          <li class="menu-icons__item">
            <v-icon @click.stop="">mdi-account-outline</v-icon>
          </li>
          <li class="menu-icons__item">
            <v-icon class="menu-icons__item-search" @click="goToSearch = true"
              >mdi-magnify</v-icon
            >
          </li>
        </ul>
      </nav>
    </header>

    <v-main>
      <MainPage :go-to-search="goToSearch" @clearProps="goToSearch = false" />
    </v-main>
  </v-app>
</template>

<script>
import MainPage from "./components/MainPage";

export default {
  name: "App",

  components: {
    MainPage,
  },

  data() {
    return {
      goToSearch: false,
      menuItems: ["Home", "Featured collections", "My profile"],
      currentPage: "Home",
    };
  },
};
</script>

<style></style>
