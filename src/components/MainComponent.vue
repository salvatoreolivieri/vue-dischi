<template>
  <main>
    <div class="sc-container">
      <div class="card-wrapper d-flex flex-wrap">
        <CardComponent />
      </div>
    </div>
  </main>
</template>

<script>
import CardComponent from './CardComponent.vue';
export default {
    name: "MainComponent",
    components: { CardComponent }
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
    border: 1px solid white;
  }

  .card-wrapper{
    width: 100%;
    border: 1px solid white;

  }
}


</style>