<template>
  <main>
    <div class="sc-container">
      <div class="card-wrapper d-flex flex-wrap">
        <CardComponent
        v-for="(item,index) in musicArray" :key="index" :musicObject="item"
        />
      </div>
    </div>
  </main>
</template>

<script>
import CardComponent from './CardComponent.vue';
import axios from "axios"

export default {
    name: "MainComponent",
    components: { CardComponent },

data(){
  return {
    baseURL: "https://flynn.boolean.careers/exercises/api/array/music",
    musicArray:[],
    isLoaded : false
  }
},

mounted(){
  this.apiRequest()
},

methods: {
  apiRequest(){
    axios.get(this.baseURL)
    .then(result => {
      this.musicArray = result.data.response;
      console.log(this.musicArray);
    })
  }
},
}

</script>

<style lang="scss" scoped>

@import "../assets/style/var";
@import "../assets/style/mixin";

main{
  background-color: $primary-color;
  // height: 500px;


  .sc-container{
    width: 70%;
    margin: 0 auto;
    padding-top: 40px;
  }

  .card-wrapper{
    width: 100%;

  }
}


</style>