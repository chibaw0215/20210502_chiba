<template>
  
  <div>
    
    <input type="text" v-model="general" />
    <button v-on:click="create">住所自動入力</button>

    <p>Address : {{this.alladdr}}</p>
  </div>
</template>

<script>
import axios from "axios";
// axiosはモジュールなのでimportする必要がある
export default {
  
  data() {
    return {
      general:"",
      
      alladdr:""
    };
  },
  methods: {
     async create() {
        let item = await axios.get(
        `https://apis.postcode-jp.com/api/v4/postcodes/${this.general}?general=true&apiKey=YCCtBxbm9ZWgsxv0T8e8py5QOUyFQYLabQ5UkI6
`
    );
    let res=item.data;
    console.log(item.data);

    this.alladdr=res[0].allAddress
    // let res =item.PromiseResult.data
    // this.alladdr=res[0].allAddress
    
   
   }
      
  }
  
  


};
</script>


<style scoped>
input {
  margin: 10px 0 10px 10px;


}
p {
  margin-left: 10px;
  margin-top: 10px;


}

</style>
