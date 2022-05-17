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

  <v-row class="konten">
    <v-col>
        <v-simple-table light>
            <template v-slot:default>
            <tbody>
                <tr>
                    <th>Id</th> 
                    <th>Nama Table</th> 
                    <th>Kode Pemesanan</th> 
                </tr>
                <tr v-for="item in pemesanan" :key="item.id">
                    <td>{{ item.id }}</td>
                    <td>{{ item.nama }}</td>
                    <td>tableKode{{ item.id }}</td>
                </tr>
            </tbody>
            
            </template>
        </v-simple-table>
    </v-col>
  </v-row>

  <v-footer dark padless>
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
  name: 'HistoryPage',
  apollo: {
      pemesanan: {
          query() {
              return gql`
              query MyQuery {
                  pemesanan {
                  id
                  nama
                  }
              }
              `
          },
          update(data){
                return data.pemesanan;
          },
          subscribeToMore: {
                document: gql`
                subscription subscribeToMore {
                    pemesanan {
                        id
                        nama
                    }
                }
                `,
                updateQuery: (previousResult, { subscriptionData }) => {
                    console.log("~ pemesanan ~ Prev", previousResult)
                    console.log("Subscribtion Data ", subscriptionData)
                    return {
                        pemesanan: subscriptionData.data.pemesanan
                    }
                },
            },

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
    .konten {
        padding: 20px;
    }
  }
</style>