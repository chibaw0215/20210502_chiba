<template>
  <div>
    <form action=""></form>
    <input type="number" v-model="general" />
    <!-- <button v-on:click="userClick">送信</button> -->

    <p>adress:{{allAddress}}</p>
  </div>
</template>

<script>
import axios from "axios";
// axiosはモジュールなのでimportする必要がある
export default {

  data() {
    return {
      general:"",
      
      allAddress:""
    };
  },
  
      
   async created() {
    
    
        const item = await axios.get(
        `https://apis.postcode-jp.com/api/v4/postcodes/{this.general}?apiKey=YCCtBxbm9ZWgsxv0T8e8py5QOUyFQYLabQ5UkI6
`
    );
    const address = item.data;
    this.allAddress=address.allAddress;
    
   }
     
  
  
  


};
</script>


<style scoped>

</style>
