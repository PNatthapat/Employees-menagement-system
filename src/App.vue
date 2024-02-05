<template>
  <header>
    <h1>Employees menagement system</h1>
  </header>
  <formComponent @save="insertEmployee" />
  <section class="employee-content" v-if="employees.length > 0">
    <h2>Employees Information</h2>
    <listData :_employees="employees" />
  </section>
</template>

<script>
import listData from "./components/listData.vue";
import formComponent from "./components/formComponent.vue";

export default {
  name: "App",
  components: {
    listData,
    formComponent,
  },
  data() {
    return {
      employees: [],
    };
  },
  methods: {
    insertEmployee(data) {
      this.employees.push(data);
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  margin: 0;
}
header {
  box-shadow: 0 2px 8px black;
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  background-color: rgb(225, 167, 95);
  color: white;
  text-align: center;
}
.employee-content {
  box-shadow: 0 2px 8px black;
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}
.employee-content h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: darkcyan;
  margin: 0 0 1rem 0;
}
</style>
