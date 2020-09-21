<template>
  <div class="text-center">
    <v-pagination
      v-model="page"
      :length="pages"
      :total-visible="7"
    ></v-pagination>
  </div>
</template>

<script>
export default {
  name: "PPagination",
  props: {
    pages: Number,
    page: Number,
  }
}
</script>

<style>

</style>