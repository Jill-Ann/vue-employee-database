<script>
  export default {
    name: 'employee-form',
    data() {
      return {
        submitting: false,
        error: false,
        success: false,
        employee: {
          name: '',
          email: '',
        },
      }
    },
    computed: {
        invalidName() {
            return this.employee.name == ''
        },
        invalidEmail() {
            return this.employee.email == ''
        },
    },
    methods: {
        handleSubmit() {
            this.$emit('add:employee', this.employee)

        clearStatus() {
            this.success = false
            this.error = false
        },
    },
  }
</script>

<template>
  <div id="employee-form">
    <form @submit.prevent="handleSubmit">
      <label>Employee name</label>
      <input v-model="employee.name" type="text" />
      <label>Employee Email</label>
      <input v-model="employee.email" type="text" />
      <button>Add Employee</button>
    </form>
  </div>
</template>

<style scoped>
  form {
    margin-bottom: 2rem;
  }

  [class*='-message'] {
    font-weight: 500;
  }

  .error-message {
    color: #d33c40;
  }

  .success-message {
    color: #32a95d;
  }
</style>