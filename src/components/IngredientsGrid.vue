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
              <span
                class="text-h3 font-weight-light"
                v-text="flour.toFixed(1)"
              ></span>
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

    <v-row>
      <v-col>
        <div class="text-center">
          <v-btn color="deep-purple" dark @click="sheet = !sheet">
            Adjust Ratios
          </v-btn>
          <v-bottom-sheet v-model="sheet">
            <v-sheet class="text-center" height="200px">
              <div>
                <v-slider
                  v-model="activeRatios.salt"
                  :label="'salt'"
                  thumb-label="always"
                  class="px-4 pt-4"
                  color="deep-purple"
                ></v-slider>

                <v-slider
                  v-model="activeRatios.water"
                  :label="'water'"
                  thumb-label="always"
                  class="px-4"
                  color="deep-purple"
                ></v-slider>

                <v-slider
                  v-model="activeRatios.starter"
                  :label="'starter'"
                  thumb-label="always"
                  class="px-4 pb-0"
                  color="deep-purple"
                ></v-slider>
              </div>

              <v-row>
                <v-col>
                  <v-btn
                    class="pb-8"
                    text
                    color="deep-purple"
                    @click="resetRatios"
                  >
                    reset
                  </v-btn>
                </v-col>
                <v-col>
                  <v-btn class="pb-8" text color="red" @click="sheet = !sheet">
                    close
                  </v-btn>
                </v-col>
              </v-row>
            </v-sheet>
          </v-bottom-sheet>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    flour: 40,
    sheet: false,

    defaultRatios: {
      salt: 25,
      water: 80,
      starter: 40,
    },

    activeRatios: {
      salt: 25,
      water: 80,
      starter: 40,
    },
  }),

  computed: {
    salt() {
      return ((this.activeRatios.salt / 100) * this.flour).toFixed(1);
    },
    starter() {
      return ((this.activeRatios.starter / 100) * this.flour).toFixed(1);
    },
    water() {
      return ((this.activeRatios.water / 100) * this.flour).toFixed(1);
    },
  },

  methods: {
    resetRatios() {
      for (const key in this.defaultRatios) {
        this.activeRatios[key] = this.defaultRatios[key];
      }
    },
  },
};
</script>
