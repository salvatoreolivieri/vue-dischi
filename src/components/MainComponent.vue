<template>
  <main>

    <NavComponent 
    @startSearch="filtraGenere"
    />

    <div class="sc-container">
      <div v-if="isLoaded" class="card-wrapper d-flex flex-wrap">
        <CardComponent
        v-for="(item,index) in filteredMusicGenre" :key="index" :musicObject="item"
        />
      </div>

      <div v-else class="card-wrapper d-flex flex-wrap align-items-center justify-content-center">
        <div class="lds-roller"><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div></div>
      </div>



    </div>
  </main>
</template>

<script>
import NavComponent from './NavComponent.vue';
import CardComponent from './CardComponent.vue';
import axios from "axios"

export default {
    name: "MainComponent",
    components: {NavComponent, CardComponent },

data(){
  return {
    baseURL: "https://flynn.boolean.careers/exercises/api/array/music",
    musicArray:[],
    isLoaded : false,
    selectedItem: ""

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
      this.isLoaded = true
    })
  },
  filtraGenere(selected){
    this.selectedItem = selected
    console.log("filtra tutti i generi con:", this.selectedItem);
    console.log(this.filteredMusicGenre);
  }
},

computed:{
  filteredMusicGenre(){

    let musicFilteredArray = [];
        if (this.selectedItem === "all"){
          musicFilteredArray = this.musicArray;
        } else {
          musicFilteredArray = this.musicArray.filter( item => {
            return item.genre.toUpperCase().includes(this.selectedItem.toUpperCase());
          })
        }
        return musicFilteredArray;

    // let musicFilteredArray = [];
    // if (musicFilteredArray.length == 0) {
    //   musicFilteredArray = this.musicArray;
    // } else{
    //   musicFilteredArray = this.musicArray.filter(item =>{
    //     return item.genre.toUpperCase().includes(this.selectedItem.toUpperCase())
    //   })
    // }
    // return musicFilteredArray;
  }
}

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
    padding-top: 20px;
  }

  .card-wrapper{
    width: 100%;
  }

  .lds-roller {
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
}
.lds-roller div {
  animation: lds-roller 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
  transform-origin: 40px 40px;
}
.lds-roller div:after {
  content: " ";
  display: block;
  position: absolute;
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #fff;
  margin: -4px 0 0 -4px;
}
.lds-roller div:nth-child(1) {
  animation-delay: -0.036s;
}
.lds-roller div:nth-child(1):after {
  top: 63px;
  left: 63px;
}
.lds-roller div:nth-child(2) {
  animation-delay: -0.072s;
}
.lds-roller div:nth-child(2):after {
  top: 68px;
  left: 56px;
}
.lds-roller div:nth-child(3) {
  animation-delay: -0.108s;
}
.lds-roller div:nth-child(3):after {
  top: 71px;
  left: 48px;
}
.lds-roller div:nth-child(4) {
  animation-delay: -0.144s;
}
.lds-roller div:nth-child(4):after {
  top: 72px;
  left: 40px;
}
.lds-roller div:nth-child(5) {
  animation-delay: -0.18s;
}
.lds-roller div:nth-child(5):after {
  top: 71px;
  left: 32px;
}
.lds-roller div:nth-child(6) {
  animation-delay: -0.216s;
}
.lds-roller div:nth-child(6):after {
  top: 68px;
  left: 24px;
}
.lds-roller div:nth-child(7) {
  animation-delay: -0.252s;
}
.lds-roller div:nth-child(7):after {
  top: 63px;
  left: 17px;
}
.lds-roller div:nth-child(8) {
  animation-delay: -0.288s;
}
.lds-roller div:nth-child(8):after {
  top: 56px;
  left: 12px;
}
@keyframes lds-roller {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

}


</style>