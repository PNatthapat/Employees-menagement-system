<template>
  <li>
    <img
      src="https://cdn-icons-png.flaticon.com/128/12930/12930579.png"
      alt=""
    />
    <br />
    <slot name="card-header"></slot>
    <slot name="card-button"></slot>
    <slot name="card-content"></slot>
  </li>
</template>

<script>
export default {};
</script>

<style scoped>
li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background: rgb(216, 169, 99);
  padding: 0.5rem;
  color: rgb(255, 255, 255);
  border-radius: 25px;
}
img {
  width: 5rem;
  height: 5rem;
}
</style>
