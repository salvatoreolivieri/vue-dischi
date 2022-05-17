<template>

  <header>
    <div class="container-fluid d-flex justify-content-between align-items-center">

      <div class="img-container">
        <img src="../assets/img/spotify-logo.png" alt="">
      </div>

      <div class="element-container d-flex align-item-center">
        <input type="text" placeholder="Search">
      </div>

      <div class="element-container">
          <select name="" id="">
            <option selected value="">Seleziona un genere</option>
            <option value="">Rap</option>
            <option value="">Rock</option>
            <option value="">Jazz</option>
          </select>
      </div>

    </div>
  </header>
  
</template>

<script>
export default {
name: "HeaderComponent"
}
</script>

<style lang="scss" scoped>

@import "../assets/style/var";

header{
  height: 110px;
  padding: 20px;
  background-color: $secondary-color;

  .img-container{
    width: 70px;
    height: 70px;

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