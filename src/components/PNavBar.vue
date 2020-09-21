<template>
 <v-app-bar app height="100" class="px-8 grey lighten-4">
    <v-btn class="fire-gradient" large dark>
      <v-icon>equalizer</v-icon>
    </v-btn>

    <v-divider class="mx-6" inset vertical></v-divider>

    <v-btn class="white" :elevation="50" large>
      <v-icon >security</v-icon>
    </v-btn>
    <v-btn class="fire-gradient" large dark>
      <v-icon >person</v-icon>
    </v-btn>

    <v-text-field
      class="ml-10 mb-0 align-end" 
      label="Pesquisar..."
      append-icon="mdi-magnify"
      with="50"
      hide-details 
      single-line>
    </v-text-field>

    <v-spacer></v-spacer>

    <div>
      <v-btn class="ma-1 white" @click.stop="setDrawer" large>
        <v-icon>tune</v-icon>
      </v-btn>
      <v-btn class="ma-1" color="pink darken-1" large dark>
        <v-icon left>person</v-icon>
        INCLUIR USUÁRIO
      </v-btn>
    </div>

    <v-divider class="mx-6" inset vertical></v-divider>

    <div>
      <v-icon class="px-4">home</v-icon>
      <v-icon class="px-4">settings</v-icon>
      <v-icon class="px-4">power_settings_new</v-icon>
    </div>
  </v-app-bar>
</template>

<script>
import store from '../store.js';

export default {
  name: "PUserTable",
  methods: {
    setDrawer() {
      store.drawer = ! store.drawer;
    }
  }
}
</script>

<style lang="scss" scoped>
.fire-gradient {
  background: rgb(223,64,64);
  background: linear-gradient(45deg, rgb(255, 0, 0) 0%, rgb(255, 153, 0) 100%);
}

.v-btn {
  min-width: 0px !important;
}
</style>