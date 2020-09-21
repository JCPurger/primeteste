<template>
  <div>
    <p-navbar></p-navbar>
    
    <p-sidebar></p-sidebar>

    <v-main>
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-col class="text-center">
            <p-data-table></p-data-table>
          </v-col>
        </v-row>
      </v-container>
    </v-main>

    <p-footer></p-footer>
  </div>
</template>

<script>
import PDataTable from '@/components/PDataTable.vue';
import PFooter from '@/components/PFooter.vue';
import PNavBar from '@/components/PNavBar.vue';
import PSideBar from '@/components/PSideBar.vue';

export default {
  name: 'PUserTable',
  components: {
    'p-data-table': PDataTable,
    'p-footer': PFooter,
    'p-navbar': PNavBar,
    'p-sidebar': PSideBar,
  },
  props: {
    source: String,
  },
  data: () => ({
    drawer: null
  }),
}
</script>


<style lang="scss" scoped>

</style>