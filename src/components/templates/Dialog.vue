<template>
  <div>
    <template>
      <v-subheader
              v-if="dialog.header"
              :key="dialog.header"
      >
        {{ dialog.header }}
      </v-subheader>

      <v-divider
              v-else-if="dialog.divider"
              :key="index"
              :inset="dialog.inset"
      ></v-divider>

      <v-list-tile
              v-else
              :key="dialog.title"
              avatar
              @click=""
      >
        <v-list-tile-avatar>
          <img :src="dialog.avatar">
        </v-list-tile-avatar>

        <v-list-tile-content>
          <v-list-tile-title v-html="dialog.title"></v-list-tile-title>
          <v-list-tile-sub-title v-html="dialog.subtitle"></v-list-tile-sub-title>
        </v-list-tile-content>
      </v-list-tile>
    </template>
  </div>
</template>

<script>
    export default {
        props: [
            "dialog"
        ],
        name: "Dialog"
    }
</script>

<style scoped>

</style>