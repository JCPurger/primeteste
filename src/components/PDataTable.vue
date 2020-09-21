<template>
  <div>

    <v-data-table
      class="elevation-1 mx-10 mt-4"
      :headers="headers"
      :items="desserts"
      :page.sync="page"
      @page-count="pageCount = $event"
      items-per-page="5"
      item-key="name"
      show-select
      single-select
    >
      <template v-slot:item.status="{ item }">
        <span class="bolder-text" :class="getColor(item.status)">{{ item.status }}</span>
      </template>
      <template v-slot:item.actions="{ item }">
        <v-icon
          small
          class="mr-2"
          @click="editItem(item)"
        >
          more_horiz
        </v-icon>
      </template>
    </v-data-table>

    <div class="text-center ma-6">
      <v-pagination v-model="page" :length="pageCount"></v-pagination>
    </div>
  </div>
</template>

<script>

export default {
    name: 'PDataTable',
    data: () => ({
      colorClass: {
        'green-text': true,
        'red-text': false,
      },
      headers: [
        {
          text: 'Usuário',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: 'Email', value: 'email' },
        { text: 'Data de inclusão', value: 'created_at' },
        { text: 'Data de alteração', value: 'updated_at' },
        { text: 'Regras', value: 'rules' },
        { text: 'Status', value: 'status' },
        { 
          text: 'Ações',
          value: 'actions',
          sortable: false
        },
      ],
      desserts: [
        {
          name: 'Frozen Yogurt',
          email: 'email@teste.com',
          created_at: '28/05/2020',
          updated_at: '20/09/2020',
          rules: '01',
          status: 'ATIVO',
        },
        {
          name: 'Ice cream sandwich',
          email: 'email@teste.com',
          created_at: '28/05/2020',
          updated_at: '20/09/2020',
          rules: '01',
          status: 'ATIVO',
        },
        {
          name: 'Eclair',
          email: 'email@teste.com',
          created_at: '28/05/2020',
          updated_at: '20/09/2020',
          rules: '01',
          status: 'ATIVO',
        },
        {
          name: 'Cupcake',
          email: 'email@teste.com',
          created_at: '28/05/2020',
          updated_at: '20/09/2020',
          rules: '01',
          status: 'ATIVO',
        },
        {
          name: 'Gingerbread',
          email: 'email@teste.com',
          created_at: '28/05/2020',
          updated_at: '20/09/2020',
          rules: '01',
          status: 'ATIVO',
        },
        {
          name: 'Jelly bean',
          email: 'email@teste.com',
          created_at: '28/05/2020',
          updated_at: '20/09/2020',
          rules: '01',
          status: 'ATIVO',
        },
        {
          name: 'Lollipop',
          email: 'email@teste.com',
          created_at: '28/05/2020',
          updated_at: '20/09/2020',
          rules: '01',
          status: 'ATIVO',
        },
        {
          name: 'Honeycomb',
          email: 'email@teste.com',
          created_at: '28/05/2020',
          updated_at: '20/09/2020',
          rules: '01',
          status: 'ATIVO',
        },
        {
          name: 'Donut',
          email: 'email@teste.com',
          created_at: '28/05/2020',
          updated_at: '20/09/2020',
          rules: '01',
          status: 'ATIVO',
        },
        {
          name: 'KitKat',
          email: 'email@teste.com',
          created_at: '28/05/2020',
          updated_at: '20/09/2020',
          rules: '01',
          status: 'ATIVO',
        },
      ],
    }),
    methods: {
      getColor (status) {
        if(status == "ATIVO") return 'green-text'
        else return 'red-text'
      },
      editItem (item) {
        this.editedIndex = this.desserts.indexOf(item)
        this.editedItem = Object.assign({}, item)
        this.dialog = true
      },
      deleteItem (item) {
        const index = this.desserts.indexOf(item)
        confirm('Are you sure you want to delete this item?') && this.desserts.splice(index, 1)
      },
    }
}
</script>

<style>
.red-text {
  color: red;
}

.green-text {
  color: #3bbf29;
}

.bolder-text {
  font-weight: 700;
}
</style>