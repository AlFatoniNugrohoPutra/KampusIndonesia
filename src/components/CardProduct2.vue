<template>
  <div class="card shadow card-product">
    <img :src=" 'assets/images/' + product.gambar " class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title"><strong>{{ product.nama }}</strong></h5>
      <p
        class="card-text"
      >Tanggal : {{ product.tanggal }} <br>Via : {{ product.via }}</p>
      <router-link class="btn btn-outline-primary" :to="'/info/'+product.id"><b-icon-book></b-icon-book> Lihat Detail</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardProduct2",
  props: ["product"],
};
</script>

<style>
</style>