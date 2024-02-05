<template>
  <cardIt>
    <template v-slot:card-header
      ><h1>Name:{{ name }}</h1></template
    >

    <template v-slot:card-content
      ><h3>Gender: {{ gender }}</h3>
      <h3>Salary: {{ salary }} baht / Position:{{ department }}</h3>
      <h3>Skills: {{ skill }}</h3></template
    >
  </cardIt>
</template>

<script>
import cardIt from "./cardIt.vue";
export default {
  name: "personData",
  components: {
    cardIt,
  },
  props: {
    id: {
      type: Number,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    salary: {
      type: Number,
      required: true,
    },
    department: {
      type: String,
      required: true,
    },
    gender: {
      type: String,
      required: true,
    },
    skill: {
      type: String,
    },
  },
  mounted() {},
};
</script>

<style scoped>
button {
  font: inherit;
  cursor: 0 border 1px solid rgb(235, 51, 51);
  background: rgb(197, 32, 32);
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px darkblue;
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s linear;
}
</style>
