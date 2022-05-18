<template>

  <section class="d-flex justify-content-between align-items-center">
    <div class="container-fluid d-flex justify-content-between align-items-center">

      <div class="img-container">
        <img src="../assets/img/spotify-logo.png" alt="">
      </div>

      <div class="element-container">
          <select 
          @change="$emit('startSearch', selected)"
          v-model="selected">
            <option disabled value="">Seleziona un genere</option>
            <option>all</option>
            <option>pop</option>
            <option>rock</option>
            <option>metal</option>
            <option>Jazz</option>
          </select>
      </div>

    </div>
  </section>
  
</template>

<script>
export default {
name: "NavComponent",

data(){
  return{
    selected: ''
  }
},

}
</script>

<style lang="scss" scoped>

@import "../assets/style/var";
@import "../assets/style/mixin";
// @import "../assets/style/general";

section{
  height: 80px;
  padding: 0px 10px;
  background-color: $secondary-color;

  .img-container{
    width: 50px;
    height: 50px;

    img{
      width: 100%;
    }
  }

  input{
    width: 400px;
    padding: 2px 10px;
    border-radius: 4px;
    border: none;

    &:focus{
      outline: none;
    }
  }

  select{
    padding: 4px 10px;
    border-radius: 4px;
    border: none;
    
  }

}

</style>