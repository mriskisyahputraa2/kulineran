<template>
  <div class="card shadow card-product">
    <img :src="'assets/img/' + product.gambar" class="card-img-top" alt="...">
    <div class="card-body">
      <h5 class="card-title">{{ product.nama }}</h5>
      <p class="card-text">Harga: {{product.harga}} </p>
      <router-link :to="'/foods/' + product.id" class="btn btn-success"><i class="fa fa-cart-shopping"></i> Pesan</router-link> <!--disini ketika user mengklick Pesan, maka akan menuju ke halaman detailfoods dengan id-nya-->
    </div>
  </div>
</template>
<script>
  export default {
    name: 'CardProduct',
    props: ['product'] // ditangkap oleh props
  }
</script>

<style>

</style>