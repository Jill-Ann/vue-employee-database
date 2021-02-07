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