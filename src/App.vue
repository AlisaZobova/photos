<template>
  <v-app>
    <header>
      <nav>

        <v-spacer></v-spacer>

        <ul class="menu-links">
          <li class="menu-links__item"><a href="#">Home</a></li>
          <li class="menu-links__item"><a href="#">Featured collections</a></li>
          <li class="menu-links__item"><a href="#">My profile</a></li>
        </ul>

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
