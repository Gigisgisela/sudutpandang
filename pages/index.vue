<template>
<div class="container">
  <v-app-bar color="#F96734">
    <img src="../assets/logo.png" height="24px" alt="">
    <v-btn rounded depressed elevation="3" class="ml-auto" to="/riwayatTransaksi">
    Riwayat Transaksi
    </v-btn>
  </v-app-bar>

  <v-row>
      <v-col>
        <v-img 

          class="jumbotron"
          :src="'https://ik.imagekit.io/gisela/hero_image_EWqjAIkeL.png?ik-sdk-version=javascript-1.4.3&updatedAt=1652723019490'"
          height="250px"
        >
          <div class="mx-auto my-auto">
            <h3 class="text-center">DELICACY AND COMFORT<br>IS<span> NUMBER ONE</span></h3>
          </div>

          <div class="text-center mt-3">
            <v-btn rounded small color="#F96734" dark to="/produk">All Product</v-btn>
          </div>
          
          
          
        </v-img>      
      </v-col>
    </v-row>
  
  
  <div class="about">
  <v-row>
    
    <v-col>
      <img 
      :src="'https://ik.imagekit.io/gisela/about_oL-msFBnE.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1652724042972'" 
      alt=""
      width="100%"
      >
    </v-col>
    <v-col>
      <h3>About Us</h3>
      <p>Sudut pandang cafe is a cafe with the best food and the best plance. Because we provide a view that can make you feel more comfortable and calm.sudut pandang cafe always guarantees the quality of its products,provides satisfactory servis,offers cleanliness and safety of food products and other added values.consumer’s smile is important to us</p>
    </v-col>
  </v-row>
  </div>
  
  <div class="contact">
  <v-row>
    
    <v-col>
      <img 
      :src="'https://ik.imagekit.io/gisela/pexels-andrea-piacquadio-3772524_MBfj6AAQK.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1652724894352'" 
      alt=""
      width="100%"
      >
    </v-col>
    <v-col>
      <h3>Contact</h3>
      <p>Email      : sudutpandang@gmail.com
        <br>
        Instagram  : @sudutpandang
        <br>
        Telp       : 08X XXXX XXXX
        <br>
        Alamat     : Jl.Dago No. 01  Bandung, Jawa Barat
      </p>
      
    </v-col>
  </v-row>
  </div>

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
export default {
  name: 'HomePage',
}
</script>

<style scoped>
  @media only screen and (min-width: 450px) {
    .container {
      max-width: 450px;
      background-color: #f1f1f1;
      padding: 0;
    }
    .jumbotron h3 {
      color: #fff;
      font-size: 16px;
      font-weight: 300;
      padding-top: 80px;
    }
    .jumbotron h3 span{
      font-weight: 700;
    }
    .about {
      background-color: #fff;
      padding: 20px;
    }
    .about p {
      font-size: 12px;
    }

    .contact {
      padding: 20px;
    }
    .contact p {
      font-size: 12px;
    }
    
  }
</style>