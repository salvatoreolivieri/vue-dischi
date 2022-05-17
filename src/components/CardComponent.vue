<template>
  <div class="sc-card">

    <div class="img-container">
      <img :src="musicObject.poster" alt="">
    </div>

    <div class="text-center my-2">
      <h4>{{musicObject.title}}</h4>
      <span>{{musicObject.author}}</span><br>
      <span>{{musicObject.year}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  props: {
    musicObject : Object
    }
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
  margin:0px 10px;
  margin-bottom: 15px;

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