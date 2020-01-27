<template>
  <div>

    <EmployeesTable
      :employees="employees"
      @select-employee="setEmployee"
    />

    <v-snackbar v-model="snackbar">
      You have selected {{ selectedEmployeeFulText }}
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
  import EmployeesTable from '../components/EmployeesTable'
  import employees from '@/data/employees.json'

  export default {
    components: {
      EmployeesTable
    },

    data () {
      return {
        selectedEmployee: {
          name: '',
          title: ''
        },
        snackbar: false,
        employees
      }
    },

    computed: {
      selectedEmployeeFulText () {
        return `${this.selectedEmployee.name} ${this.selectedEmployee.title}`
      }
    },

    methods: {
      setEmployee (employee) {
        this.snackbar = true
        this.selectedEmployee = employee
      }
    }
  }
</script>
