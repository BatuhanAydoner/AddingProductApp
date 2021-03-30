<template>
  <div class="col-md-11 card">
    <div class="card-body">
      <div class="form-group">
        <label>Product Name</label>
        <input
          type="text"
          class="form-control"
          placeholder="Enter product name"
          v-model="productName"
        />
      </div>
      <div class="row">
        <div class="form-group col-md-6">
          <label>Product Quantity</label>
          <input
            type="text"
            class="form-control"
            placeholder="Enter product quantity"
            v-model="productCount"
          />
        </div>
        <div class="form-group col-md-6">
          <label>Product Price</label>
          <input
            type="text"
            class="form-control"
            placeholder="Enter product price"
            v-model="productPrice"
          />
        </div>
      </div>
      <button class="btn btn-outline-info btn-block" @click="add">Add!</button>
    </div>
  </div>
</template>

<script>
import { vm } from "../main";
export default {
  data() {
    return {
      productName: null,
      productCount: null,
      productPrice: null,
      selectedImage: null,
    };
  },
  methods: {
    add: function () {
      this.productName &&
        this.productCount &&
        this.productPrice &&
        vm.$emit("addedProduct", {
          name: this.productName,
          quantity: this.productCount,
          price: this.productPrice,
          total: parseInt(this.productPrice) * parseInt(this.productCount),
          selectedImage: this.selectedImage ? this.selectedImage : null,
        });

      this.productName = null;
      this.productCount = null;
      this.productPrice = null;
      this.selectedImage = null;
    },
  },
  created() {
    vm.$on("addedImage", (image) => {
      this.selectedImage = image;
      console.log(image);
    });
  },
};
</script>
