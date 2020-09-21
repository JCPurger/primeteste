<template>
  <v-footer color="black" absolute app >
    <v-spacer></v-spacer>
    <span class="white--text">&copy; {{ new Date().getFullYear() }}</span>
  </v-footer>
</template>

<script>
export default {
  name: 'PFooter'
}
</script>