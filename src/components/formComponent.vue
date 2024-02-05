<template>
  <form @submit.prevent="submitForm">
    <div class="form-control">
      <label for="emp-name">Name:</label>
      <input type="text" v-model.trim="employee.name" />
    </div>
    <div class="form-control">
      <label for="salary">Salary:</label>
      <input type="number" v-model="employee.salary" />
    </div>
    <div class="form-control">
      <label for="salary">department</label>
      <select v-model="employee.department">
        <option value="Marketing">Marketing</option>
        <option value="Accounting">Accounting</option>
        <option value="Engineering">Engineering</option>
      </select>
    </div>
    <div class="form-control">
      <h2>Gender</h2>
      <div>
        <input type="radio" value="Male" v-model="employee.gender" />
        <label for="gender-name">Male</label>
      </div>
      <div>
        <input type="radio" value="Female" v-model="employee.gender" />
        <label for="gender-name">Female</label>
      </div>
    </div>
    <div class="form-control">
      <h2>Language</h2>
      <div>
        <input type="checkbox" value="english" v-model="employee.skill" />
        <label for="skill">English</label>
      </div>
      <div>
        <input type="checkbox" value="china" v-model="employee.skill" />
        <label for="skill">China</label>
      </div>
      <div>
        <input type="checkbox" value="india" v-model="employee.skill" />
        <label for="skill">India</label>
      </div>
    </div>
    <div class="form-control">
      <button>Save</button>
    </div>
  </form>
</template>

<script>
export default {
  name: "formComponent",
  data() {
    return {
      employee: {
        name: "",
        salary: 0,
        department: "Marketing",
        gender: "",
        skill: [],
      },
    };
  },
  methods: {
    submitForm() {
      const newEmployee = {
        name: this.employee.name,
        salary: this.employee.salary,
        department: this.employee.department,
        gender: this.employee.gender,
        skill: this.employee.skill,
      };
      this.$emit("save", newEmployee);
      this.resetForm();
    },
    resetForm() {
      this.employee.name = "";
      this.employee.salary = 0;
      this.employee.department = "Marketing";
      this.employee.gender = "";
      this.employee.skill = [];
    },
  },
};
</script>

<style scoped>
form {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0 2px 4px rgb(116, 111, 111);
  padding: 2rem;
  background: white;
}
.form-control {
  margin: 0.5rem 0;
}
label {
  font-weight: bold;
}
input,
select {
  display: block;
  width: 100%;
  font: inherit;
  margin-top: 0.5rem;
}
button {
  font: inherit;
  background: rgb(209, 75, 97);
  color: white;
  cursor: pointer;
  padding: 0.5rem 1rem;
  border-radius: 10px;
  width: 25%;
}
input[type="radio"] {
  display: inline-block;
  width: auto;
  margin-right: 1rem;
}
input[type="checkbox"] {
  display: inline-block;
  width: auto;
  margin-right: 1rem;
}
input[type="radio"] + label {
  font-weight: normal;
}
input[type="checkbox"] + label {
  font-weight: normal;
}
h2 {
  font-size: 1rem;
  margin: 0.5rem 0;
}
</style>
