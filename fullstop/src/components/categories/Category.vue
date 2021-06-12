<template>
  <div class="d-flex flex-row justify-content-center">
    <button class="item" :id="id">
      {{ name }}
    </button>
  </div>
</template>

<script>
export default {
  name: "Categories",
  props: ["id", "name"],
};
</script>

<style scoped>
.item {
  border: 1px solid white;
  color: #a6bcd0;
  border-radius: 48px;
  background-color: white;
  font-size: 16px;
}
</style>
