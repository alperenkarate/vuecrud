<template>
  <div id="dashboard">
    <ul class="collection with-header">
      <li class="collection-header">
        <h4>Employees</h4>
      </li>
      <li
        v-for="employee in employees"
        v-bind:key="employee.id"
        class="collection-item"
      >
        {{ employee.employee_id }} {{ employee.name }}
        <router-link
          class="secondary-content"
          v-bind:to="{
            name: 'view-employee',
            params: { employee_id: employee.employee_id },
          }"
        >
          <i class="fa fa-eye"></i>
        </router-link>
      </li>
    </ul>
    <div class="fixed-action-btn">
      <router-link to="/new" class="btn-floating btn-large red">
        <i class="fa fa-plus"></i>
      </router-link>
    </div>
  </div>
</template>

<script>
import db from "./firebaseInit";

export default {
  name: "dashboard",
  data() {
    return {
      employees: [],
    };
  },
  mounted() {
    db.collection("employees")
      //   .orderBy("employee_id")
      .get()
      .then((querySnapshot) => {
        querySnapshot.forEach((doc) => {
          const data = {
            id: doc.id,
            employee_id: doc.data().employee_id,
            name: doc.data().name,
            dept: doc.data().dept,
            position: doc.data().position,
          };
          this.employees.push(data);
        });
      });
  },
};
</script>

<style>
</style>