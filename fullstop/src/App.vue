<template>
  <div id="app">
    <Header />
    <Categories :categories="categories" @eventname="changeCategory" />
    <div class="row d-flex flex-row justify-content-around align-items-center">
      <div class="card-columns col-md-8 col-sm-12 col-xs-12">
        <Card
          v-for="item in products"
          :key="item.id"
          :id="item.id"
          :imageSrc="item.image"
          :price="item.price"
          :title="item.title"
        />
      </div>
    </div>
    <Footer :categories="categories" />
  </div>
</template>

<script>
import Header from "./components/header/Header.vue";
import Categories from "./components/categories/Categories.vue";
import axios from "axios";
import Card from "./components/card/Card.vue";
import Footer from "./components/footer/Footer.vue"

export default {
  name: "App",
  components: {
    Header,
    Categories,
    Card,
    Footer
  },
  data() {
    return {
      categories: null,
      products: null,
      selectedCategory: null,
    };
  },
  methods: {
    changeCategory(variable) {
      this.selectedCategory = variable;
      this.updatePage();
    },
    updatePage() {
      if (this.selectedCategory == "All") {
        axios.get("https://fakestoreapi.com/products").then((res) => {
          this.products = res.data;
        });
      } else {
        axios
          .get(
            `https://fakestoreapi.com/products/category/${this.selectedCategory}`
          )
          .then((res) => {
            this.products = res.data;
          });
      }
    },
    ucWord(word) {
      return word && word.length >= 2
        ? word[0].toUpperCase() + word.substring(1)
        : "";
    },
  },
  mounted: function () {
    axios.get("https://fakestoreapi.com/products/categories").then((res) => {
      let newCategories = [];
      for (let i = 0; i < res.data.length; i++) {
        newCategories.push({
          name: res.data[i],
          id: i + 1,
          title: this.ucWord(res.data[i]),
        });
      }
      this.categories = [
        { name: "All", id: "0", title: "All" },
        ...newCategories,
      ];
    });
    axios.get("https://fakestoreapi.com/products").then((res) => {
      this.products = res.data;
    });
  },
};
</script>

<style>
.card-columns {
  display: inline-block;
  margin-top: 12px;
}
@media (max-width: 768px) {
  .card-columns {
    column-count: 1;
  }
}

@media (min-width: 768px) {
  .card-columns {
    column-count: 2;
  }
}

@media (max-width: 913px) {
  .card-columns {
    column-count: 3;
  }
}
@media (min-width: 1200px) {
  .card-columns {
    column-count: 4;
  }
}

* {
  text-align: center;
  list-style-type: none;
}
</style>
