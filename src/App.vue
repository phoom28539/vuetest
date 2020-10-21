<template>
  <div id="app" class="small-container">
    <h1>Employees</h1>
    <employee-table :employees="employees" />
  </div>
</template>

<script>
import EmployeeTable from '@/components/EmployeeTable'
export default {
  name: 'App',
  components:{
    EmployeeTable
  },
  data() {
    return {
      employees: [
        {
          id: 1,
          name: 'phoom jr',
          email: 'phoom@hotmail.com',
        },
        {
          id: 2,
          name: 'Te jr',
          email: 'Ter@hotmail.com',
        },
        {
          id: 3,
          name: 'plo jr',
          email: 'plor@hotmail.com',
        }
      ]
    }
  }
}
</script>

<style>
  .small-container {
    max-width: 680px;
  }
</style>
