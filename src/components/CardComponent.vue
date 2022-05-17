<template>
  <div class="sc-card">

    <div class="img-container">
      <img src="../assets/img/Antares.jpg" alt="">
    </div>

    <div class="text-center my-2">
      <h4>Antares</h4>
      <span>Ours Samplus</span><br>
      <span>2004</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
}
</script>

<style lang="scss" scoped>

@import "../assets/style/var";
@import "../assets/style/mixin";
// @import "../assets/style/general";

.sc-card{
  background-color: $secondary-color;
  padding: 10px;
  width: calc((100% / 5) - 20px);
  padding-bottom: 45px;
  margin:0px 10px;
  margin-bottom: 20px;

  .img-container{

    img{
    width: 100%;
    }
  }

  h4{
    text-transform: uppercase;
    color: white;
    font-size: 16px;
  }

  span{
    color: #7D7977;
  }

  
}

</style>