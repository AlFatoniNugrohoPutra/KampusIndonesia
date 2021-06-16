<template>
  <div class="hero">
    <!-- Desktop -->
    <div class="d-none d-md-block">
      <div class="row mt-4">
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2 class="title_hero">
                <strong>Bingung Cari Informasi Seputar Kuliah ?</strong>
                <br />Cari Disini aja !
              </h2>
              <p class="title_hero">Dapatkan informasi seputar dunia perkuliahan secara terupdate dari kami melalui aplikasi Kampus Indonesia</p>
              <router-link class="btn btn-lg btn-outline-primary tombol" to="/login">
                <b-icon-arrow-right></b-icon-arrow-right>Login
              </router-link>
              <div class="row mt-3">
                <div class="col">
                  <div class="input-group mb-3">
                    
                    <input
                      v-model="search"
                      type="text"
                      class="form-control"
                      placeholder="Informasi Seputar Perkuliahan/Cari Kampus"
                      aria-label="Cari"
                      aria-describedby="basic-addon1"
                      @keyup="searchAll"
                    />

                    <div class="input-group-prepend">
                      <span class="input-group-text" id="basic-addon1">
                        <b-icon-search></b-icon-search>
                      </span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <img src="../assets/images/banner.svg" width="100%" />
        </div>
      </div>
    </div>

    <!-- Mobile -->
    <div class="d-sm-block d-md-none">
      <div class="row mt-4">
        <div class="col-md-6 mb-3">
          <img src="../assets/images/hero.png" width="100%" />
        </div>
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2>
                <strong>Bingung Cari Informasi Seputar Kuliah ?</strong>
                <br />Cari Disini aja !
              </h2>
              <p>Dapatkan informasi seputar dunia perkuliahan secara terupdate dari kami melalui aplikasi Kampus Indonesia</p>
              <button class="btn btn-lg btn-success">
                <b-icon-arrow-right></b-icon-arrow-right>Pesan
              </button>
              <div class="row mt-3">
                <div class="col">
                  <div class="input-group mb-3">
                    
                    <input
                      v-model="search"
                      type="text"
                      class="form-control"
                      placeholder="Cari Makanan Kesukaan Anda .."
                      aria-label="Cari"
                      aria-describedby="basic-addon1"
                      @keyup="searchAll"
                    />

                    <div class="input-group-prepend">
                      <span class="input-group-text" id="basic-addon1">
                        <b-icon-search></b-icon-search>
                      </span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Hero",
  data() {
    return {
      products: [],
      search: '',
    };
  },
  methods: {
    setProducts(data) {
      this.products = data;
    },
    searchAll() {
      axios
      .get("http://localhost:3000/products?q="+this.search)
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error));
    }
  },
  mounted() {
    axios
      .get("http://localhost:3000/products")
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style>
</style>