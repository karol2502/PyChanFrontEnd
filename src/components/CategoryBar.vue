<template>
  <v-card class="mx-16 my-8">
    <v-item-group mandatory>
      <v-container>
        <v-row class="d-flex justify-start ml-8">
          <v-col
              v-for="category in categories"
              :key="category"
              cols="4"
              md="4"
          >
            <v-item v-slot="{active, toggle}">
              <v-card
                  :color="active ? 'primary' : ''"
                  class="d-flex align-center text-center"
                  height="60"
                  @click="toggle(); clickedCategory(category)"
              >
                <div class="text-h5 flex-grow-1 text-center">
                  {{ category }}
                </div>
              </v-card>
            </v-item>
          </v-col>
        </v-row>
      </v-container>
    </v-item-group>
  </v-card>
</template>

<script>
import axios from "axios";

const API = 'http://37.190.226.156:5000/';

export default {
  name: "CategoryBar",
  data: function () {
    return {
      categories: [],
    }
  },
  methods: {
    clickedCategory(category) {
      this.$emit('clickedCategory', category)
    }
  },
  created() {
    axios.get(`${API}categories`)
        .then((response) => {
          this.categories = response.data.result;
        })
        .catch((error) => {
          console.log(error);
        });
  },
}
</script>
