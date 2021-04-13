<template>
  <div id="app">
    <input type="text" v-model="coad" value="zipcoadを取得">
    <button @click="zipcoad(coad)">住所自動入力</button>
    <p>Adress:{{ adress }}</p>

  </div>
  
</template>

<script>
import axios from "axios"
export default{
  data(){
    return{
      coad:""
    }

  },

  methods:{
    zipcoad(){
      url = "https://apis.postcode-jp.com/api/v4/" + this.coad + '?apiKey=' + ViYTWVzJn5CupAeLkQRxCuxs4TtSZPQLZaMBaBw;

      axios.get(url).then(response => {this.json = response ["coad"]})
       

      

    }

    }

  }



</script>
