<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in this.$root.cart" :key="product.id">
      <div class="info">
        <h1>{{product.name}}</h1>
        <p>{{product.country}}</p>
      </div>
      <div class="image">
        <img :src="'/images/products/'+product.image">
      </div>
      <div class="price">
        <h2>{{product.price}}</h2>
        <button class="auto" @click="removeFromCart(product)">Remove From Cart</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
    name: 'Cart',
    methods:{
    removeFromCart(product){
      this.$root.$data.cart.splice(this.$root.$data.cart.indexOf(product),1)
    }
  }
}
</script>