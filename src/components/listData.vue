<template>
  <ul>
    <personData
      v-for="(item, index) in _employees"
      :key="index"
      :name="item.name"
      :salary="item.salary"
      :department="item.department"
      :gender="item.gender"
      :skill="item.skill"
    />
  </ul>
</template>

<script>
import axios from "axios";
import personData from "./person.vue";

export default {
  name: "listData",
  components: {
    personData,
  },
  data() {
    return {
      employees: null,
    };
  },
  mounted() {
    this.loadData();
  },
  methods: {
    async loadData() {
      const response = await axios.get("/data.json");
      console.log(response.data);
      this.employees = response.data.employees;
    },
  },
  props: ["_employees"],
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}
</style>
