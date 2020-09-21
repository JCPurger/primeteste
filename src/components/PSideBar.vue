<template>
  <v-navigation-drawer v-model="drawer" absolute temporary right>
    <v-list dense>
      <v-list-item link>
        <v-list-item-action>
          <v-icon>mdi-home</v-icon>
        </v-list-item-action>

        <v-list-item-content>
          <v-list-item-title>Home</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-list-item link>
        <v-list-item-action>
          <v-icon>mdi-email</v-icon>
        </v-list-item-action>

        <v-list-item-content>
          <v-list-item-title>Contact</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
import store from '../store.js';

export default {
  name: "PSideBar",
  data() {
    return {
      drawer: store.drawer,
    }
  }
}
</script>

<style>

</style>