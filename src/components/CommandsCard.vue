<template>
  <v-card class="mx-16">
    <v-container>
      <v-expansion-panels>
        <CommandPanel
            v-for="command in commands"
            :key="command.id"
            :command="command"
        />
      </v-expansion-panels>
    </v-container>
  </v-card>
</template>

<script>
import CommandPanel from "./CommandPanel";

export default {
  props: ['commands'],
  name: "CommandsCard",
  components: {
    CommandPanel,
  }
}
</script>

