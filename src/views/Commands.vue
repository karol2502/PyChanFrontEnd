<template>
  <v-app>
    <v-main>
      <v-card class="mx-16 my-8">
        <v-container>
          <v-item-group mandatory>
            <v-row class="d-flex justify-start ml-16">
              <v-col
                  v-for="category in categories"
                  :key="category"
                  cols="2"
                  md="2"
              >
                <v-item v-slot="{active, toggle}">
                  <v-card
                      :color="active ? 'primary' : ''"
                      class="d-flex align-center"
                      height="60"
                      @click="toggle(); clickedCategory(category)"
                  >
                    <div class="display-1 flex-grow-1 text-center">
                      {{ category }}
                    </div>
                  </v-card>
                </v-item>
              </v-col>
            </v-row>
          </v-item-group>
        </v-container>
      </v-card>
      <v-card class="mx-16">
        <v-container>
          <v-expansion-panels
              accordion
              class="my-8"
              v-for="command in commands"
              :key="command.id">
            <v-expansion-panel>
              <v-expansion-panel-header>
                <v-container>
                  <div class="title">{{ command.name }}</div>
                  <v-divider class="my-4"></v-divider>
                  <div class="subtitle-1">{{ command.descripion }}</div>
                </v-container>
              </v-expansion-panel-header>
              <v-expansion-panel-content>
                <div class="subtitle-1 font-weight-bold">Składnia</div>
                <div>
                  <span
                      v-for="syntax in command.syntax"
                      v-bind:key="syntax"
                  >
                    {{ syntax }}
                  </span>
                </div>
                <div class="aliases" v-if="command.aliases !== undefined">
                  <div class="subtitle-1 font-weight-bold mt-4">Aliasy</div>
                  <div>
                    <span
                        v-for="alias in command.aliases"
                        v-bind:key="alias"
                    >
                      {{ alias }}
                    </span>
                  </div>
                </div>
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-container>

      </v-card>
    </v-main>
  </v-app>
</template>

<script>
import axios from 'axios';

const API = 'http://37.190.226.156:5000/';

export default {
  name: "Commands",
  data: () => ({
    categories: [],
    commands: [],
  }),
  methods: {
    clickedCategory(category) {
      axios.get(`${API}${category}`)
          .then((response) => {
            this.commands = response.data.result;
          })
          .catch((error) => {
            console.log(error);
          });
    }
  },
  created() {
    axios.get(`${API}categories`)
        .then((response) => {
          this.categories = response.data.result;
          this.clickedCategory(this.categories[0]);
        })
        .catch((error) => {
          console.log(error);
        });
  },
}

</script>
