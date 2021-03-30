<template>
  <div class="row product-container">
    <div class="col-md-2 card" v-for="(item, index) in products" :key="index">
      <img class="card-img-top" src="/src/assets/default.png" alt="Card image cap" />
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <small> <strong>Quantity : </strong> 1 </small>
        <br />
        <small> <strong>Price : </strong> 10 </small>
        <br />
        <small> <strong>Total : </strong> 10 </small>
      </div>
    </div>
  </div>
</template>

<script>
import { vm } from "../main";
export default {
  data() {
    return {
      products: [],
    };
  },
  created() {
    vm.$on("addedProduct", (product) => {
      this.products.push({ product });
    });
  },
};
</script>
