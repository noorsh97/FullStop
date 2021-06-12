<template>
  <div class="categories row align-items-center">
    <div class="d-flex flex-row justify-content-center">
      <div class="d-flex flex-row justify-content-center">
        <button
          class="item"
          v-for="item in categories"
          :key="item.id"
          :id="item.id"
          :name="item.name"
          :class="['item', selectedItemId == item.id ? 'focused' : '']"
          @click="changeCategoryType"
        >
          {{ item.title }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Categories",
  props: ["categories", "eventname"],
  data() {
    return {
      selectedItemId: 0,
    };
  },
  methods: {
    changeCategoryType(event) {
      this.selectedItemId = event.target.id;
      this.$emit("eventname", event.target.name);
    },
  },
};
</script>

<style scoped>
.categories {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  height: 100px;
}
.item {
  border: 1px solid white;
  color: #a6bcd0;
  border-radius: 48px;
  background-color: white;
  font-size: 16px;
}
.focused {
  background-color: #7bed8d;
  color: white;
}
</style>
