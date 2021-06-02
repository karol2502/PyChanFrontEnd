<template>
  <v-expansion-panel>
    <v-expansion-panel-header>
      <v-container>
        <div class="title">{{ command.name }}</div>
        <v-divider class="my-4"></v-divider>
        <div class="subtitle-1">{{ command.description }}</div>
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
      <div class="aliases" v-if="command.aliases.length !== 0">
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
</template>

<script>
export default {
  props: ['command'],
  name: "CommandPanel"
}
</script>
