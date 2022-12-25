<template>
  <div>
    <ul @click="$emit('toggle-menu')" class="burger">
      <li></li>
      <li></li>
      <li></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Burger",
};
</script>

<style scoped>
div {
  display: none;
}

.burger {
  padding: 10px 10px;
  background-color: #fff;
  flex-direction: column;
  border-radius: 0.25rem;
  gap: 5px;
}

.burger:hover {
  cursor: pointer;
}

li {
  width: 30px;
  height: 2px;
  background-color: #333;
}

@media (max-width: 992px) {
  div {
    display: block;
  }
}
</style>
