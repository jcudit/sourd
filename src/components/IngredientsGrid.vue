<template>
  <v-container class="grey lighten-5">
    <v-row>
      <v-col>
        <v-card class="pa-8" tile>
          <v-row>
            <v-col>
              <span class="text-h3 font-weight-light" v-text="salt"></span>
              <span class="subheading font-weight-light">grams</span>
            </v-col>
            <v-col>
              <v-card-text>Salt</v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>

    <v-row>
      <v-col>
        <v-card class="pa-8" tile>
          <v-row>
            <v-col>
              <span class="text-h3 font-weight-light" v-text="water"></span>
              <span class="subheading font-weight-light">grams</span>
            </v-col>
            <v-col>
              <v-card-text>Water</v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>

    <v-row>
      <v-col>
        <v-card class="pa-8" tile>
          <v-row>
            <v-col>
              <span class="text-h3 font-weight-light" v-text="starter"></span>
              <span class="subheading font-weight-light">grams</span>
            </v-col>
            <v-col>
              <v-card-text>Starter</v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>

    <v-row>
      <v-col>
        <v-card class="pa-8" tile>
          <v-row>
            <v-col>
              <span class="text-h3 font-weight-light" v-text="flour.toFixed(2)"></span>
              <span class="subheading font-weight-light">grams</span>
            </v-col>
            <v-col>
              <v-card-text>Flour</v-card-text>
            </v-col>
          </v-row>
          <v-row>
            <v-slider v-model="flour" thumb-label></v-slider>
          </v-row>
        </v-card>
      </v-col>
    </v-row>


  </v-container>
</template>

<script>
export default {
  data: () => ({
    flour: 40,
  }),

  computed: {
    salt() {
      return (0.25 * this.flour).toFixed(2);
    },
    starter() {
      return (0.8 * this.flour).toFixed(2);
    },
    water() {
      return (0.4 * this.flour).toFixed(2);
    },
  },
};
</script>
