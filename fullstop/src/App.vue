<template>
  <div id="app">
    <Header />
    <Categories :categories="categories" v-on:change-cat="changeCategory" />
    <div class="row d-flex flex-row justify-content-around align-middle mb-5 mt-5 mx-auto">
      <div class="col-md-8 col-sm-12 col-xs-12 m-auto">
        <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 g-4">
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
      categories: ['all'],
      products: null,
    };
  },
  methods: {
    changeCategory(variable) {
      this.updatePage(variable);
    },
    updatePage(variable) {
      if (variable == "all") {
        axios.get("https://fakestoreapi.com/products").then((res) => {
          this.products = res.data;
        });
      } else {
        axios
          .get(
            `https://fakestoreapi.com/products/category/${variable}`
          )
          .then((res) => {
            this.products = res.data;
          });
      }
    },
  },
  mounted: function () {
    axios.get("https://fakestoreapi.com/products/categories").then((res) => {
      this.categories = [...this.categories, ...res.data]
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

@media (max-width: 575.98px) {
.card-columns {
  column-count: 1;
}
}

@media (min-width: 576px) and (max-width: 767.98px) { 
.card-columns {
  column-count: 1;
}
 }


@media (min-width: 768px) and (max-width: 991.98px) { 
.card-columns {
  column-count: 2;
}
}


@media (min-width: 992px) and (max-width: 1199.98px) { 
.card-columns {
  column-count: 2;
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
