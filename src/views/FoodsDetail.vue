<template>
  <div class="food-detail">
    <Navbar />
    <div class="container">

        <!-- breadcrumb -->
      <div class="row mt-5">
        <div class="col">
          <nav aria-label="breadcrumb">
            <ol class="breadcrumb">
              <li class="breadcrumb-item">
                <router-link to="/" class="text-dark">Home</router-link>
              </li>
              <li class="breadcrumb-item">
                <router-link to="/foods" class="text-dark">Foods</router-link>
              </li>
              <li class="breadcrumb-item active" aria-current="/foods ">Foods Order</li>
            </ol>
          </nav>
        </div>
      </div>
      <!-- End breadcrumb -->

    <div class="row">
        <div class="col-md-6">
            <img :src="'../assets/img/' + product.gambar" class="img-fluid shadow" style="border-radius:10px; ">
        </div>
        <div class="col-md-6">
            <h2><strong>{{ product.nama }}</strong></h2><hr>
            <h4>Harga: <strong>Rp. {{ product.harga}}</strong></h4>
        </div>
    </div>

    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import axios from 'axios'

export default {
  name: "FoodsDetail",
  components: {
    Navbar
  },
  data(){
    return{
        product: {}
    }
  },
  methods:{
    setProduct(data){
        this.product = data
    }
  },
  mounted(){
      axios
      .get("http://localhost:3000/products/" +this.$route.params.id)
      .then(response => this.setProduct(response.data)) 
      .catch(error => console.log("Gagal: ", error));
  }
};
</script>

<style>
</style>