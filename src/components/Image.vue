<template>
    <div class="card-body tex-center d-flex align-items-center flex-column">
        <img height="128" class="img-responsive text-center mb-3"
               :src="product.selectedImage == null ? './src/assets/default.png' : product.selectedImage">
          <input ref="file" type="file" style="display: none;" @change="onChange($event)" class="form-control">
          <button class="btn btn-outline-secondary " type="button" @click="$refs.file.click()">Resim Seç</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            product : {
            selectedImage: null
        },
        }
    },
    methods: {
        onChange(e) {
        const file = e.target.files[0];
        this.product.selectedImage = URL.createObjectURL(file);
      }
    },
}
</script>