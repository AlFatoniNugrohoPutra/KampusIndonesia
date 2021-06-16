<template>
  <section>
    <div class="d-none d-md-block">
      <div class="row mt-4">
        <div class="col-md-6">
          <img src="../assets/images/Lowongan.svg" width="100%" />
        </div>

        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2>
                <strong>Apakah Kamu Sedang Mencari Pekerjaan ?</strong>
              </h2>
              <p>Temukan Pekerjaan Terbaik Kamu Disini.</p>
              <router-link class="btn btn-lg btn-outline-primary" to="/">
                Cari Lowongan
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Lowongan",
};
</script>

<style>
</style>