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
      general:""

    };
  },
  methods: {
    
    userClick () {
      const item =axios.get(
      `https://apis.postcode-jp.com/api/v4/postcode/postcode/postcode=${this.general}&allAddress=""apiKey=YCCtBxbm9ZWgsxv0T8e8py5QOUyFQYLabQ5UkI6
`
    );
    
    const address =item.data;
    this.allAddress=address.allAddress;

    }
  }
  
  
};
</script>


<style scoped>

</style>

