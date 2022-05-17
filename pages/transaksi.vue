<template>
<div class="container">
    <v-app-bar color="#F96734" class="mb-3"></v-app-bar>
    <v-row class="text-center mt-2">
        <v-col>
            <h3>Pemesanan Anda Telah Berhasil Dilakukan</h3>
        </v-col>  
    </v-row>
    <v-row class="text-center mt-4 mb-4">
        <v-col>
            <img width="60%" src="../assets/check.svg" alt="">
        </v-col>  
    </v-row>
    <v-row class="text-center">
        <v-col>
            <p>Lihat kode pesanan pada riwayat transaksi untuk verifikasi kepada pihak Sudut Pandang</p>
        </v-col>
    </v-row>
    <v-row class="text-center">
        <v-col>
            <p>Terimakasih atas pemesanan anda</p>
        </v-col>
    </v-row>
    <v-row class="text-center">
        <v-col>
            <v-btn block large dark color="#F96734" to="/">Kembali ke Beranda</v-btn>
        </v-col>
    </v-row>

    
</div>
</template>

<script>
export default {
    name: 'transaksiPage',
    
}
</script>

<style scoped>
  @media only screen and (min-width: 450px) {
    .container {
      max-width: 450px;
      background-color: #f1f1f1;
      padding: 0;
    }
  }
</style>