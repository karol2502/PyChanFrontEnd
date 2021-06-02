<template>
  <v-main>
    <v-row no-gutters>
      <v-col
          md="8"
          offset-md="2"
      >
        <CategoryBar @clickedCategory="clickedCategory"/>
        <CommandsCard class="mb-16" :commands="commands"/>
      </v-col>
    </v-row>
  </v-main>
</template>

<script>
import axios from 'axios';
import CategoryBar from "../components/CategoryBar.vue";
import CommandsCard from "../components/CommandsCard";

const API = 'http://37.190.226.156:5000/';

export default {
  name: "Commands",
  components: {
    CategoryBar,
    CommandsCard,
  },
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
