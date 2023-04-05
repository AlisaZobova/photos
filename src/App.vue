<template>
  <v-app>
    <header class="page-header">
      <nav>
        <v-spacer />

        <ul class="menu-links">
          <li class="menu-links__item"><a href="#">Home</a></li>
          <li class="menu-links__item"><a href="#">Featured collections</a></li>
          <li class="menu-links__item"><a href="#">My profile</a></li>
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
            <v-list-item class="menu-links__item">
              <v-list-item-title> Home </v-list-item-title>
            </v-list-item>
            <v-list-item class="menu-links__item">
              <v-list-item-title> Featured collections </v-list-item-title>
            </v-list-item>
            <v-list-item class="menu-links__item">
              <v-list-item-title> My profile </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>

        <ul class="menu-icons">
          <li class="menu-icons__item"><v-icon>mdi-account-outline</v-icon></li>
          <li class="menu-icons__item"><v-icon>mdi-magnify</v-icon></li>
        </ul>
      </nav>
    </header>

    <v-main>
      <MainPage />
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
};
</script>

<style></style>
