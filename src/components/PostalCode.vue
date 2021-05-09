<template>
  <div>
    <form action=""></form>
    <input type="number" v-model="general" />
    <button v-on:click="created">送信</button>

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
  method: {
    async created() {
    
    
        const item = await axios.get(
        `https://apis.postcode-jp.com/api/v4/postcodes/{this.general}&apiKey=YCCtBxbm9ZWgsxv0T8e8py5QOUyFQYLabQ5UkI6
`
    );
    
    const addr = item.data;
    this.address=addr.allAddress;
    
   }
     
  }
  
  


};
</script>


<style scoped>

</style>
