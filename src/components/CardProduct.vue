<template>
  <div class="card shadow card-product">
    <img :src=" 'assets/images/' + product.gambar " class="card-img-top" alt="..." />
    <img :src=" 'assets/images/' + product.logo " class="card-logo" alt="..." />
    <div class="card-body">
      <h5 class="card-title">{{ product.nama }}</h5>
      <p
        class="card-text"
      ><strong>Akreditasi : {{ product.akreditasi }}</strong></p>
      <router-link class="btn btn-outline-primary" :to="'/info/'+product.id"><b-icon-book></b-icon-book> Lihat Detail</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardProduct",
  props: ["product"],
};
</script>

<style>
</style>