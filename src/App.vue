<template>
  <div id="app">
    <input type="text" v-model="coad" value="zipcoadを取得">
    <button @click="zipcoad(coad)">住所自動入力</button>
    <p>Adress:{{ this.address }}</p>

  </div>
  
</template>

<script>
import axios from "axios"
export default{
  data(){
    return{
      coad:"",
      address:"",
    }

  },

  methods:{
    
    async zipcoad(){
      const url = `https://apis.postcode-jp.com/api/v4/postcodes/${this.coad}?apiKey=ViYTWVzJn5CupAeLkQRxCuxs4TtSZPQLZaMBaBw`;

      axios.get(url).then((response) => { 
      
       this.address = response.data[0].allAddress
       console.log(response)
       response.data[0].allAddress});

      


      
      
      
    }

    }

  }

</script>
