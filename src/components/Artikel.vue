<template>
  <div class="artikel">
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      style="text-shadow: 1px 1px 2px #333;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <b-carousel-slide img-src="assets/images/Bajak.jpg" class="img_slide">
        <b-badge class="badge_slide" pill variant="light">Artikel</b-badge>
        <h1 class="title_slide">Hati-Hati Penipuan <br />di Sosial Media Anda</h1>
        <p class="desc_slide">17 Desember 2020</p>
      </b-carousel-slide>

      <b-carousel-slide img-src="assets/images/Marah.jpg" class="img_slide">
        <b-badge class="badge_slide" pill variant="light">Artikel</b-badge>
        <h1 class="title_slide">Kenapa Marah Bisa <br />Memperpendek Usia</h1>
        <p class="desc_slide">4 Maret 2020</p>
      </b-carousel-slide>

      <b-carousel-slide img-src="assets/images/Depresi.jpg" class="img_slide">
        <b-badge class="badge_slide" pill variant="light">Artikel</b-badge>
        <h1 class="title_slide">Salah Pilih Jurusan <br />Banyak Membuat Mahasiswa Tidak Lulus</h1>
        <p class="desc_slide">26 November 2020</p>
      </b-carousel-slide>

      <b-carousel-slide img-src="assets/images/Masker.jpg" class="img_slide">
        <b-badge class="badge_slide" pill variant="light">Artikel</b-badge>
        <h1 class="title_slide">Musim Corona Harus <br />Menggunakan Masker Saat Berpergian</h1>
        <p class="desc_slide">10 April 2020</p>
      </b-carousel-slide>

    </b-carousel>
  </div>
</template>

<script>
export default {
  name: "Artikel",
};
</script>

<style>
</style>