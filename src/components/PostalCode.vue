<template>
  <div>
    <form action=""></form>
    <input type="number" v-model="general" name="general"/>
    <input type="submit" v-on:click="userClick" name="general"/>

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
  methods: {
    
    userClick () {
      

    
        const result =axios.get(
        `/postcodes/{this.general}&apiKey=YCCtBxbm9ZWgsxv0T8e8py5QOUyFQYLabQ5UkI6
`
    );
    return console.log(result);
    
    
      }
  
  }
  


};
</script>


<style scoped>

</style>
