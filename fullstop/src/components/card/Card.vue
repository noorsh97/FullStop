<template>
<div class="col-12 d-flex align-items-stretch">
  <div class="card flex-fill">
    <div class="card-body d-flex align-items-center justify-content-center">
      <img :src="imageSrc" class="card-img-top" :alt="title">
    </div>
    <div class="card-footer">
      <h5 class="card-title">{{ title }}</h5>
      <p class="card-text">JOD {{ price }}</p>
    </div>
  </div>
</div>
</template>

<script>
  export default {
    name: "Card",
    props: ["imageSrc", "price", "title"],
  };
</script>

<style scoped>
  .cardObject {
    justify-content: center;
    align-items: center;
    width: 100%;
    min-height: 351px;
    border: 1px solid white;
    margin: 16px;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    color: #748a9d;
    justify-content: flex-start;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    transition: 0.3s;
  }
  .card .card-footer{
    background: transparent;
    border: none;
  }
  .card .card-title{
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
  }
  .card img {
    width: auto;
    max-width: 100%;
    max-height: 255px;
    margin-bottom: 20px;
    padding: 0 20px
  }

  .imageContainer {
    text-align: center;
    margin: 20px;
  }
  .title {
    width: 230px;
    height: 35px;
    font-size: 16pt;
    margin-left: 15px;
    margin-right: 15px;
    margin-bottom: 20px;
    overflow: hidden;
  }
  .price {
    font-weight: bold;
    margin-bottom: 20px;
    width: 60px;
    height: 17px;
  }
</style>
