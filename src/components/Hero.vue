<template>
  <div class="hero">
    <div class="d-none d-md-block">
      <!-- Tampilan Desktop -->
      <div class="row mt-4">
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2>
                <strong>Delicious Food Menu,</strong>
                <br />in Your Cadget
              </h2>
              <p>Ayo pesan dan pilih makanan favorit kamu, SEKARANG!!!</p>
              <router-link to="/foods" class="btn btn-lg btn-success">
                <i class="fa fa-arrow-right"></i> PESAN
              </router-link>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <img src="../assets/img/hero.png" width="100%" alt />
        </div>
      </div>
      <!-- End Desktop -->
    </div>

      <!-- Tampilan Mobile -->
    <div class="d-sn-block d-md-none">
      <div class="row mt-4">
        <div class="col-md-6 mb-3">
          <img src="../assets/img/hero.png" width="100%" alt />
        </div>
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2>
                <strong>Delicious Food Menu,</strong>
                <br />in Your Cadget
              </h2>
              <p>Ayo pesan dan pilih makanan favorit kamu, SEKARANG!!!</p>
              <button class="btn btn-lg btn-success">
                <i class="fa fa-arrow-right"></i> PESAN
              </button>
            </div>
          </div>
        </div>
      </div>
      <!-- End Mobile -->
    </div>
</template>

<script>
export default {
  name: "Hero"
};
</script>

<style>
</style>