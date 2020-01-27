<template>
  <div>
    <v-data-table
      :headers="headers"
      :items="employees"
      :items-per-page="5"
      class="elevation-1"
      @click:row="selectRow"
    ></v-data-table>

    <v-snackbar v-model="snackbar">
      You have selected {{ currentItem }}
      <v-btn
        color="pink"
        text
        @click="snackbar = false"
      >Close
      </v-btn>
    </v-snackbar>
  </div>
</template>

<script>
  import employees from '@/data/employees.json'

  export default {
    data () {
      return {
        currentItem: '',
        snackbar: false,
        headers: [
          { text: 'ID', align: 'left', sortable: false, value: 'id' },
          { text: 'Name', value: 'name' },
          { text: 'Title', value: 'title' },
          { text: 'Salary', value: 'salary' },
        ],
        employees
      }
    },

    methods: {
      selectRow (event) {
        this.snackbar = true
        this.currentItem = `${event.name} | ${event.title}`
      }
    }
  }
</script>
