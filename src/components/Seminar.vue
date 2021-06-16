<template>
    <div>
        <div class="row mt-4">
            <div class="col">
            <h2>
                Best
                <strong style="color:#143b81">Seminar</strong>
            </h2>
            </div>
            <div class="col">
            <router-link to="/seminar" class="btn btn-outline-primary float-right">
                <b-icon-eye></b-icon-eye>Lihat Semua
            </router-link>
            </div>
        </div>

        <div class="row mb-4">
            <div class="col-md-4 mt-4" v-for="product in products" :key="product.id">
            <CardProduct2 :product="product" />
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";

import CardProduct2 from "@/components/CardProduct2.vue";
export default {
  name: "Seminar",
  components: {
    CardProduct2,
  },
  data() {
    return {
      products: [],
    };
  },
  methods: {
    setProducts(data) {
      this.products = data;
    }
  },
  mounted() {
    axios
      .get("http://localhost:3000/seminar")
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style>
</style>