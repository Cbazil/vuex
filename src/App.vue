<template>
  <div id="app">
      <ProductListOne></ProductListOne>
      <ProductListTwo></ProductListTwo>
  </div>
</template>

<script>
import ProductListOne from './components/ProductListOne.vue';
import ProductListTwo from './components/ProductListTwo.vue';

export default {
  components: {
    'ProductListOne': ProductListOne,
    'ProductListTwo': ProductListTwo
  },
  name: 'app',
  data () {
    return {
      // products: [
      //   { name: 'Banana Skin', price: 20 },
      //   { name: 'Shiny Star', price: 40 },
      //   { name: 'Green Shells', price: 60 },
      //   { name: 'Red Shells', price: 80 },
      // ]
    }
  }
}
</script>

<style>

body {
  font-family: Ubuntu;
  color: #555;
}

</style>
