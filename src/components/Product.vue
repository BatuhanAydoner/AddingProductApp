<template>
    <div class="col-md-11 card">
          <div class="card-body">
            <div class="form-group">
              <label>Ürün Adı</label>
              <input type="text" class="form-control" placeholder="adını giriniz" v-model="productName">
            </div>
            <div class="row">
              <div class="form-group col-md-6">
                <label>Ürün Adeti</label>
                <input type="text" class="form-control" placeholder="adetini giriniz" v-model="productCount">
              </div>
              <div class="form-group col-md-6">
                <label>Ürün Fiyatı</label>
                <input type="text" class="form-control" placeholder="fiyatını giriniz" v-model="productPrice">
              </div>
            </div>
            <button class="btn btn-outline-info btn-block" @click="add">Ekle!</button>
          </div>
        </div>
</template>

<script>
export default {
    data() {
        return {
            productName: null,
            productCount: null,
            productPrice: null
        }
    },
    methods: {
        add: function() {
            console.log(this.productName, this.productCount, this.productPrice);
        }
    },
}
</script>