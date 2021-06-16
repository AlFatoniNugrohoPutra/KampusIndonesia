<template>
  <div class="home">
    <Navbar />
    <div class="container">
      <Hero />

      <div class="row mt-4">
        <div class="col">
          <h2>
            Best
            <strong style="color:#143b81">Perguruan Tinggi Negeri</strong>
          </h2>
        </div>
        <div class="col">
            <router-link to="/ptn" class="btn btn-outline-primary float-right">
                <b-icon-eye></b-icon-eye>Lihat Semua
            </router-link>
        </div>
      </div>

      <div class="row mb-4">
        <div
          class="col-md-4 mt-4"
          v-for="product in products"
          :key="product.id"
        >
          <CardProduct :product="product" />
        </div>
      </div>

      <div class="lokasi_kampus">
        <h1 class="title_text">Lokasi Kampus</h1>
        <Lokasi />
      </div>
    </div>
    <div class="fitur_home">
      <h1 class="title_text">Fitur Yang Tersedia di Kampus Indonesia</h1>
      <Fitur />
    </div>
    <div class="container">
      <div class="lowongan_home">
        <Lowongan />
      </div>

      <div class="seminar_home">
        <h1 class="title_text">Informasi Seminar</h1>
        <Seminar />
      </div>

      <div class="artikel_home">
        <h1 class="title_text">Artikel Terbaru Kampus</h1>
        <p class="subtitle_artikel">
          Jangan sampai terlewat informasi terbaru kampus favoritmu
        </p>
        <Artikel />
      </div>

      <div class="partner_home">
        <h1 class="title_text">Bekerja Sama Dengan</h1>
        <Partner />
      </div>
    </div>
    <div class="footer_home">
        <Footer />
      </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Hero from "@/components/Hero.vue";
import CardProduct from "@/components/CardProduct.vue";
import Lokasi from "@/components/Lokasi.vue";
import Fitur from "@/components/Fitur.vue";
import Lowongan from "@/components/Lowongan.vue";
import Seminar from "@/components/Seminar.vue";
import Artikel from "@/components/Artikel.vue";
import Partner from "@/components/Partner.vue";
import Footer from "@/components/Footer.vue";
import axios from "axios";

export default {
  name: "Home",
  components: {
    Navbar,
    Hero,
    CardProduct,
    Lokasi,
    Fitur,
    Lowongan,
    Seminar,
    Artikel,
    Partner,
    Footer,
  },
  data() {
    return {
      products: [],
    };
  },
  methods: {
    setProducts(data) {
      this.products = data;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/best-products")
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error));
  },
};
</script>