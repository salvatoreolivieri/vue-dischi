<template>
  <div>

    <MainComponent />

  </div>
</template>

<script>
import MainComponent from './components/MainComponent.vue'

export default {
  name: 'App',
  components: {
    MainComponent
},

}
</script>

<style lang="scss">

@import "./assets/style/var";
@import "./assets/style/mixin";
@import "./assets/style/general";



</style>
