<template>
  <div>

    <HeaderComponent />

    <MainComponent />

  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainComponent from './components/MainComponent.vue'
import axios from "axios"

export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent
},

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
      this.musicArray = result.data;
      console.log(this.musicArray);
    })
  }
},

}
</script>

<style lang="scss">

@import "./assets/style/var";
@import "./assets/style/mixin";
@import "./assets/style/general";



</style>
