<template>

  <div class="categories row align-items-center">
    <div class="m-auto">
      <button
        class="item"
        v-for="item of categories"
        :key="item"
        :id="item"
        :class="selectedItemId == item && 'focused'"
        @click="changeCategoryType"
      >
        {{ item }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Categories",
  props: ["categories"],
  data() {
    return {
      selectedItemId: 'all',
    };
  },
  methods: {
    changeCategoryType(event) {
      this.selectedItemId = event.target.id;
      this.$emit("change-cat", event.target.id);
    },
  },
};
</script>

<style scoped>
.categories {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  height: 100px;
  overflow: hidden;
  overflow-x: scroll;
  white-space: nowrap;
}
.item {
  border: 1px solid white;
  color: #a6bcd0;
  border-radius: 48px;
  background-color: white;
  font-size: 16px;
  padding: 18px 20px;
  min-width: 80px;
  margin: 6px;
  text-transform: capitalize;
}
.focused {
  background-color: #7bed8d;
  color: white;
}
</style>
