<template>
  <div class="cardObject">
    <div class="imageContainer">
      <img v-bind:src="imageSrc" alt="Italian Trulli" />
    </div>
    <span class="title">{{ title }}</span>
    <span class="price">{{ price }}</span>
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
    float: left;
    justify-content: center;
    align-items: center;
    width: 258px;
    height: 351px;
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

  img {
    width: 100%;
    height: 100%;
    object-fit: fill;
  }

  .imageContainer {
    width: 220px;
    height: 221px;
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
