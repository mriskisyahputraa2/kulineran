<template>
  <div>
    <Navbar />
    <div class="container">
      <div class="row mt-4">
        <div class="col">
          <h2>
            Daftar
            <strong>Makanan</strong>
          </h2>
        </div>
      </div>

      
      <div class="row mt-4">
        <div class="col">
          <div class="input-group mb-3">
            <input  
              v-model="search" 
              type="text"
              class="form-control"
              placeholder="Cari Makanan Kesukaan Anda..."
              aria-label="Cari"
              aria-describedby="basic-addon1"
              @keyup="searchFood"
            />
            <!-- v-model : berguna ketika menginput data, ketika user input data, maka @keyup="searchFood"(searchFood dari method / memanggil) akan bekerja, sesuai api yang user minta -->
            <span class="input-group-text" id="basic-addon1"><i class="fa fa-search"></i></span>
          </div>
        </div>
      </div>

      <div class="row mb-4">
        <div class="row mb-4">
          <div class="col-md-4 mt-4" v-for="product in products" :key="product.id">
            <!--mengambil data products dan change jadi product dari idnya-->
            <CardProduct :product="product" />
            <!-- dan disini untuk menampilkannya-->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import CardProduct from "@/components/CardProduct.vue";
import axios from "axios";
export default {
  name: "Food",
  components: {
    Navbar,
    CardProduct
  },
  // mulai menggunakan API
  data() {
    return {
      products: [],
      search: '' // ini data yang di kembalikan
    };
  },
  methods: {
    setProduct(data) {
      this.products = data; // mengambil product dan di simpan dalam parameter data // dan data search yang user minta akan disimpan didalam v-data.
    }, 
    searchFood() { // disini logika nya ketika user menekan tombol search 
        axios
      .get("http://localhost:3000/products?q=" +this.search) // maka data akan keluar dari api dengan menambahkan this.search 
      // dan dengan menambahkan ?q= sama seperti GET 
      .then(response => this.setProduct(response.data)) 
      .catch(error => console.log("Gagal: ", error));
    }
  },

  mounted() {
    axios
      .get("http://localhost:3000/products") // ngambil url API product
      .then(response => this.setProduct(response.data)) // beri respon dari data untuk product
      .catch(error => console.log("Gagal: ", error));
  }
};
</script>

<style>
</style>