<template>
  <div id="app" class="small-container">
    <h1>Employees</h1>
    <employee-form @add:employee="addEmployee"/>
    <employee-table 
      :employees="employees" 
      @deleteemployee="deleteEmployee" 
      @edit:employee="editEmployee"
    />
  </div>
</template>

<script>
import EmployeeTable from '@/components/EmployeeTable'
import EmployeeForm from '@/components/EmployeeForm'

export default {
  name: 'App',
  components:{
    EmployeeTable,
    EmployeeForm
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
  },
  methods: {
    addEmployee(employee){
      const lastId =
        this.employees.length > 0 ? this.employees[this.employees.length - 1].id :0;
      const id = lastId + 1;
      const newEmployee = {...employee, id};
      this.employees=[...this.employees, newEmployee]
      console.log(this.employees);
    },
    deleteEmployee(id) {
      this.employees = this.employees.filter(employee => employee.id !== id)
    },
    editEmployee(id, updatedEmployee) {
      this.employees = this.employees.map(employee => employee.id === id ? updatedEmployee : employee)
    }
  }
}
</script>

<style>

  button {
    background: #009435;
    border: 1px solid #009435;
    padding: .8em;
    color: #fff;
  }

  button:hover,
  button:active,
  button:focus{
    background: #009435;
    border: 1px solid #009435;
  }
  .small-container {
    max-width: 680px;
  }
</style>
