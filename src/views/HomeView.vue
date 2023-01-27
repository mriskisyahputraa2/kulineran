<template>
  <div class="home">
    <Navbar />
    <div class="container">
      <Hero />
      <div class="row mt-">
        <div class="col">
          <h2>
            Best
            <strong>Foods</strong>
          </h2>
        </div>
        <div class="col">
          <router-link to="/foods" class="btn btn-success"><i class="fa fa-eye"></i>Lihat Semua</router-link>
        </div>
      </div>
      
      <div class="row mb-4">
        <div class="col-md-4 mt-4" v-for="product in products" :key="product.id"> <!--mengambil data products dan change jadi product dari idnya-->
          <CardProduct :product="product"/>  <!-- dan disini untuk menampilkannya-->
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
    CardProduct,
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