<script>
import MainPage from "./components/MainPage";

export default {
  name: "App",

  components: {
    MainPage,
  },

  data: () => ({
    //
  }),
};
</script>

<template>
  <v-app >
    <v-main>
      <MainPage />
    </v-main>
  </v-app>
</template>

<style>
#app {
  background: #efefef;
}
</style>
