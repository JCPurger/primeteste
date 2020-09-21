<template>
  <v-app id="app">
    <p-user-table-page />
  </v-app>
</template>

<script>
import PUserTablePage from './views/PUserTablePage.vue'

export default {
  name: 'App',
  components: {
    "p-user-table-page": PUserTablePage
  },
  created () {
    this.$vuetify.theme.dark = false
  },
}
</script>

<style>
</style>
