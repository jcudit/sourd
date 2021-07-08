<template>
  <v-app>
    <v-app-bar app color="deep-purple" dark>
      <v-toolbar-title>sourd</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <v-container fluid class="fill-height">
        <IngredientsGrid />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import IngredientsGrid from "./components/IngredientsGrid";

export default {
  name: "sourd",

  components: {
    IngredientsGrid,
  },

  data: () => ({
    //
  }),
};
</script>
