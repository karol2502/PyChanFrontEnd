<template>
  <v-container>
    <v-row>
      <v-col
          md="8"
          offset-md="2"
          class="d-flex flex-column align-center">
        <v-img
            max-width="400"
            src="../assets/logo.png"/>
        <v-container
            class="align-center text-center">
          <p id="name">
            PyChan
          </p>
          <p id="description">
            Dołącz do użytkowników korzystających z jednego z najlepszych naukowych botów Discord
          </p>
        </v-container>
        <NeonButton/>
      </v-col>
    </v-row>

  </v-container>


</template>

<script>
import NeonButton from "../components/NeonButton";

export default {
  name: 'Home',
  components: {
    NeonButton,
  },
}
</script>

<style lang="scss" scoped>
#name {
  font-size: 6vmin;
}

#description {
  font-size: 3vmin;
}
</style>

