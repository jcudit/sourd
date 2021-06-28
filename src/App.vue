<template>
  <v-app>
    <v-app-bar app color="primary" dark> </v-app-bar>

    <v-main>
      <Ingredients />
    </v-main>
  </v-app>
</template>

<script>
import Ingredients from "./components/Ingredients";

export default {
  name: "App",

  components: {
    Ingredients,
  },

  data: () => ({
    //
  }),
};
</script>
