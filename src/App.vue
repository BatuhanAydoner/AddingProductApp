<template>
  <div class="container">
    <heading><h1 class="text-center">Adding Product App</h1><hr></heading>
    <div class="row">
      <div class="card offset-2 col-md-3">
          <product-image></product-image>
      </div>
      <div class="col-md-5">
        <product></product>
      </div>
    </div>
    <br><br>
    <div class="progress">
      <progress-bar></progress-bar>
    </div>
    <br><br>
    <h3 class="text-center">Added Products List</h3>
    <hr>
    <div class="row product-container">
      <added-products></added-products>
    </div>

  </div>


</template>

<script>
import AddedProductsVue from './components/AddedProducts.vue';
import HeadingVue from './components/Heading.vue';
import ImageVue from './components/Image.vue';
import ProductVue from './components/Product.vue';
import ProgressbarVue from './components/Progressbar.vue';
  export default {
    components: {
      heading: HeadingVue,
      productImage: ImageVue,
      product: ProductVue,
      progressBar: ProgressbarVue,
      addedProducts: AddedProductsVue,
    },
    data() {
      return {
        imageList: [],
        product : {
            selectedImage: null
        },
      }
    },
    methods: {
      
    }
  }
</script>

<style>
  body {
    background-color: aliceblue;
    padding-top: 20px;
    padding-bottom: 20px;
  }

  .card{
    margin-right: 5px;
    margin-bottom: 5px;
  }

  .card:last-child{
    margin-right: 0px;
  }

  .col-md-2{
    max-width: 15.666667%!important;
  }

  .product-container{
    margin-left: 15px;
  }

</style>

