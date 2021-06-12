<template>
  <div class="categories row align-items-center">
    <div class="col d-flex flex-row justify-content-center">
      <Category
        v-for="item in categories"
        :key="item.id"
        :id="item.id"
        :name="item.name"
      />
    </div>
  </div>
</template>

<script>
import Category from "./Category.vue";

export default {
  name: "Categories",
  props: ["categories"],
  components: {
    Category,
  },
};
</script>

<style scoped>
.categories {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
}
</style>
