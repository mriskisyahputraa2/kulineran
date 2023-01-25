<template>
  <div class="home">
    <Navbar />
    <div class="container">
      <Hero />

      <div class="row mt-4">
        <div class="col">
          <h2>
            Best
            <strong>Foods</strong>
          </h2>
        </div>

        <div class="col">
          <route-link to="/food" class="btn btn-success float-right">
            <i class="fa fa-eye"></i> Lihat semua
          </route-link>
        </div>
      </div>  

      <div class="row mb-3">
        <div clas="col-md-3 mt-4" v-for="product in products" :key="product.id"> <!--v.product akan ditampilkan, dan key untuk menampilkan api product berdasarkan id-->
          <CardProduct  :product="product"/> <!--tampilkan product-->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Hero from "@/components/Hero.vue";
import CardProduct from "@/components/CardProduct.vue";
import axios from "axios";
export default {
  name: "Home",
  components: {
    Navbar,
    Hero,
    CardProduct
  },

  // mulai menggunakan API
  data() {
    return {
      products: []
    };
  },
  methods: {
    setProduct(data) {
      this.products = data; // mengambil product dan di simpan dalam parameter data
    }
  },

  mounted() {
    axios
      .get("http://localhost:3000/best-products") // ngambil url API product
      .then((response) => this.setProduct(response.data)) // beri respon dari data untuk product
      .catch((error) => console.log("Gagal: ", error) );
  }
};
</script>