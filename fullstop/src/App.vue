<template>
  <div id="app">
    <Header />
    <Categories :categories="categories" />
  </div>
</template>

<script>
import Header from "./components/header/Header.vue";
import Categories from './components/categories/Categories.vue';
import axios from "axios";

export default {
  name: "App",
  components: {
    Header,
    Categories,
  },
  data() {
      return {
        categories: null,
      };
    },
   mounted: function() {
      axios.get("https://fakestoreapi.com/products/categories").then((res) => {
        let newCategories = [];
        for (let i = 0; i < res.data.length; i++) {
          newCategories.push({ name: res.data[i], id: i+1});
        }
        this.categories = [{name: "All", id: "0"}, ...newCategories]
      });
    },
};
</script>

<style>
</style>
