<template>
<div class="wrapper">
  <h1 v-if="this.$root.$data.cart.length > 1" style="text-align: center">Compare Vehicles</h1>
  <h1 v-if="this.$root.$data.cart.length == 0" style="text-align: center">No Vehicles to Compare :(</h1>
  <h1 v-if="this.$root.$data.cart.length == 1" style="text-align: center">Add Another Vehicle So You Can Compare Them</h1>
  
  <div class="products">
    <div class="product" v-for="product in this.$root.cart" :key="product.id">
      <div class="info">
        <h1>{{product.make}}</h1>
        <p>{{product.model}}</p>
      </div>
      <div class="image">
        <img :src="'/images/products/'+product.image">
      </div>
      <div class="price">
        <h2>{{product.price}}</h2>
        <button class="auto" @click="removeFromCart(product)">Remove From List</button>
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

<style scoped>
/* .wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
} */

.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 10px;
  margin-top: 50px;
  width: 300px;
}

.product img {
  border: 2px solid #333;
  height: 250px;
  width: 300px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #4bb9ec;
  color: rgb(20, 20, 20);
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 18px;
}

.info h2 {
  font-size: 18x;
}

.info p {
  margin: 0px;
  font-size: 10px;
}

.price {
  display: flex;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>