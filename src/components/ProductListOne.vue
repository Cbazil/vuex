<template>
  <div id="product-list-one">
      <h2>Product List One</h2>
      <ul>
        <li v-for="(product, index) in saleProducts" :key="index">
            <span class="name">{{ product.name }}</span>
            <span class="price">${{ product.price }}</span>
        </li>
      </ul>
      <button v-on:click="reducePrice(4)">Reduce Price</button>
  </div>
</template>

<script>
import { mapActions } from 'vuex';
import { mapGetters } from 'vuex';

export default {
  computed: {
    products(){
      return this.$store.state.products
    },
    // Singular way of filtering data

    // saleProducts() {
    //   var saleProducts = this.$store.state.products.map( product => {
    //     return {
    //       name: '**' + product.name + '**',
    //       price: product.price / 2,
    //     }
    //   })
    //   return saleProducts;
    // }

    // Getting Getter
    // saleProducts(){
    //   return this.$store.getters.saleProducts;
    // }

    ...mapGetters([
      'saleProducts'
    ])

  },
  methods: {
    // reducePrice() {
    //   this.$store.state.products.forEach( product => {
    //     product.price -= 1;
    //   })
    // }
    // reducePrice(amount) {
      // DIRECT MUTATION ->
      // this.$store.commit('reducePrice');
      
      // Calling action, where action exercutes mutation
    //   this.$store.dispatch('reducePrice', amount);

    // }

    ...mapActions([
      'reducePrice'
    ])
  }
}
</script>

<style scoped>

#product-list-one {
  background-color: #fff8b1;
  box-shadow:  1px 2px 3px rgba(0, 0, 0, 0.2);
  margin-bottom: 30px;
  padding: 10px 20px;
}
#product-list-one ul{
  padding: 0;
}
#product-list-one li{
  display: inline-block;
  margin-right: 10px;
  margin-top: 10px;
  padding: 20px;
  background: rgba(255, 255, 255, 0.7);
}
.price{
  font-weight: bold;
  color: #e8800c;
}

</style>