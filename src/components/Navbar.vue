<template>
    <nav class="navbar navbar-expand-lg navbar-light">
  <div class="container">
    <a class="navbar-brand" href="/">Kulineran</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
        </li>
        <li class="nav-item">
            <router-link class="nav-link" to="/foods">Foods</router-link>
        </li>
      </ul>
       <ul class="navbar-nav ml-auto ">
        <li class="nav-item">
            <router-link class="nav-link" to="/keranjang">
            Keranjang
            <i class="fa fa-cart-plus"></i>
            <!-- <span class="badge badge-success">0</span> -->
            </router-link>
        </li>
      </ul>
    </div>
  </div>
</nav>
</template>

<script>
export default {
    name: 'Navbar'
}
</script>

<style>

</style>