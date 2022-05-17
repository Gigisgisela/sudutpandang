<template>
<div class="container ">
  <v-app-bar color="#F96734" class="mb-3">
    <v-btn
      class="mx-2"
      fab
      small
      color="#fff"
      to="/"
    >
      <v-icon>
        mdi-chevron-left
      </v-icon>
    </v-btn>
  </v-app-bar>
  <v-row>
    <v-col
    v-for="(item, index) in produk"
    :key="item.id">
      <v-card
        max-width="190"
        class="mx-auto"
        light
        elevation="3"
      >
        <v-img
          height="168"
          :src="item.gambar"
        ></v-img>

        <v-card-text>
          <h3 class="mb-2">{{ item.nama }}</h3>
          <p>Rp. {{ item.harga }},-</p>
        </v-card-text>
        <v-btn block dark color="#F96734" :to="'/detailProduk' + index">View Detail</v-btn>
      </v-card>
    </v-col>
  </v-row> 

  <v-footer class="mt-4" dark padless>
    <v-col
      class="text-center"
      cols="12"
    >
      2022 — <strong>Sudut Pandang</strong>
    </v-col>
  </v-footer>
</div>
</template>

<script>
import gql from 'graphql-tag'
export default {
  name: 'ProdukPage',
   apollo: {
    produk: {
      query() {
        return gql`
          query MyQuery {
            produk {
              id
              nama
              harga
              deskripsi
              gambar
            }
          }
        `
      }
    }
  },
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