<template>
  <div class="row product-container">
    <div class="col-md-2 card" v-for="(item, index) in products" :key="index">
      <img
        class="card-img-top"
        :src="
          item.product.selectedImage
            ? item.product.selectedImage
            : `/src/assets/default.png`
        "
        alt="Card image cap"
      />
      <div class="card-body">
        <h5 class="card-title">{{ item.product.name }}</h5>
        <small> <strong>Quantity : </strong> {{ item.product.name }} </small>
        <br />
        <small> <strong>Price : </strong> {{ item.product.price }} </small>
        <br />
        <small> <strong>Total : </strong> {{ item.product.total }} </small>
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
