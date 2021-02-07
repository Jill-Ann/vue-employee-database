<script>
  export default {
    name: 'employee-table',
    props: {
        employees: Array,
    },
    data() {
      return {
        editing: null
      }
    },
    methods: {
      editMode(id) {
        this.cachedEmployee = Object.assign({}, employee)
        this.editing = id
      },

      cancelEdit(employee) {
        Object.assign(employee, this.cachedEmployee)
        this.editing = null
      },

      editEmployee(employee) {
        if (employee.name == '' || employee.email == '') return
        this.$emit('edit:employee', employee.id, employee)
        this.editing = null
      },
    }
  }
</script>

<template>
  <div id="employee-table">
    <table>
        <tbody>
            <tr v-for="employee in employees" :key="employee.id">
                <td>{{ employee.name}}</td>
                <td>{{ employee.email}}</td>
            </tr>
        </tbody>
    </table>
  </div>
</template>

<style scoped></style>