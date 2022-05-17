<template>
<div class="container">
  <v-app-bar color="#F96734">
    <v-btn
      class="mx-2"
      fab
      small
      color="#fff"
      to="/produk"
    >
      <v-icon>
        mdi-chevron-left
      </v-icon>
    </v-btn>
  </v-app-bar>

  <v-row>
    <div>
      <v-col>
        <img :src="produk[indexNumber].gambar" height="250" alt="">
      </v-col>
    </div>
  </v-row>
  
  <div class="konten">
  <v-row>
    <v-col>
      <h2>{{ produk[indexNumber].nama }}</h2>
    </v-col>
  </v-row>

  <v-row>
    <v-col>
      <h3>Rp. {{ produk[indexNumber].harga }},-</h3>
    </v-col>
  </v-row>

  <v-row>
    <v-col>
      <h3>Deskripsi :</h3>
    </v-col>
  </v-row>
  <v-row>
    <v-col>
      <p>{{ produk[indexNumber].deskripsi }}</p>
    </v-col>
  </v-row>
  </div>
  
  <v-row>
    <v-col>
      <v-btn block large dark color="#F96734" @click="bookingTable(produk[indexNumber].nama)" to="/transaksi"  >Booking Table</v-btn>
    </v-col>
  </v-row>
      
</div>
    
    

</template>

<script>
import gql from 'graphql-tag'
export default {
  name: 'DetailPage',
  computed: {
        indexNumber() {
            return this.$route.params.detailProduk.slice(12)
        }
  },
  data() {
    return {
      
    }
  },
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
  
  methods: {
    bookingTable(namaKode) {
      this.$apollo.mutate({
          mutation: gql`
            mutation MyMutation($nama: String) {
                insert_pemesanan(objects : {nama: $nama}) {
                    returning {
                        id
                        nama
                    }
                }
            }

          `,
          variables: {
          nama: namaKode,
          }
          
      })
  
    }
  }
  
}
</script>

<style scoped>
  @media only screen and (min-width: 450px) {
    .container {
      max-width: 450px;
      background-color: #f1f1f1;
      padding: 0;
    }
    .konten {
      padding: 20px;
    }
  }
</style>