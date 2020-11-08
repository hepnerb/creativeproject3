<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('Honda')" href="#" class="pure-menu-link">Honda</a></li>
      <li class="pure-menu-item"><a @click="select('Dodge')" href="#" class="pure-menu-link">Dodge</a></li>
      <li class="pure-menu-item"><a @click="select('Lexus')" href="#" class="pure-menu-link">Lexus</a></li>
      <li class="pure-menu-item"><a @click="select('Geo')" href="#" class="pure-menu-link">Geo</a></li>
      <li class="pure-menu-item"><a @click="select('Audi')" href="#" class="pure-menu-link">Audi</a></li>
      <li class="pure-menu-item"><a @click="select('Lamborghini')" href="#" class="pure-menu-link">Lamborghini</a></li>
      <li class="pure-menu-item"><a @click="select('Mitsubishi')" href="#" class="pure-menu-link">Mitsubishi</a></li>
      <li class="pure-menu-item"><a @click="select('Ford')" href="#" class="pure-menu-link">Ford</a></li>
      <li class="pure-menu-item"><a @click="select('Volkswagen')" href="#" class="pure-menu-link">Volkswagen</a></li>
      <li class="pure-menu-item"><a @click="select('Subaru')" href="#" class="pure-menu-link">Subaru</a></li>
      <li class="pure-menu-item"><a @click="select('Buick')" href="#" class="pure-menu-link">Buick</a></li>
      <li class="pure-menu-item"><a @click="select('Kia')" href="#" class="pure-menu-link">Kia</a></li>
      <li class="pure-menu-item"><a @click="select('Land Rover')" href="#" class="pure-menu-link">Land Rover</a></li>
      <li class="pure-menu-item"><a @click="select('Tesla')" href="#" class="pure-menu-link">Tesla</a></li>
      <li class="pure-menu-item"><a @click="select('GMC')" href="#" class="pure-menu-link">GMC</a></li>
      <li class="pure-menu-item"><a @click="select('Chevrolet')" href="#" class="pure-menu-link">Chevrolet</a></li>
      <li class="pure-menu-item"><a @click="select('Jeep')" href="#" class="pure-menu-link">Jeep</a></li>


    </ul>
  </div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class = "pure-menu-list">
      
      <li class="pure-menu-item"><a @click="select('Maserati')" href="#" class="pure-menu-link">Maserati</a></li>
      <li class="pure-menu-item"><a @click="select('Mercedes-Benz')" href="#" class="pure-menu-link">Mercedes-Benz</a></li>
      <li class="pure-menu-item"><a @click="select('Mercury')" href="#" class="pure-menu-link">Mercury</a></li>
      <li class="pure-menu-item"><a @click="select('Lincoln')" href="#" class="pure-menu-link">Lincoln</a></li>
      <li class="pure-menu-item"><a @click="select('Suzuki')" href="#" class="pure-menu-link">Suzuki</a></li>
      <li class="pure-menu-item"><a @click="select('Cadillac')" href="#" class="pure-menu-link">Cadillac</a></li>
      <li class="pure-menu-item"><a @click="select('Porsche')" href="#" class="pure-menu-link">Porsche</a></li>
      <li class="pure-menu-item"><a @click="select('Mazda')" href="#" class="pure-menu-link">Mazda</a></li>
      <li class="pure-menu-item"><a @click="select('Toyota')" href="#" class="pure-menu-link">Toyota</a></li>
      <li class="pure-menu-item"><a @click="select('Oldsmobile')" href="#" class="pure-menu-link">Oldsmobile</a></li>
      <li class="pure-menu-item"><a @click="select('Nissan')" href="#" class="pure-menu-link">Nissan</a></li>
      <li class="pure-menu-item"><a @click="select('Volvo')" href="#" class="pure-menu-link">Volvo</a></li>
      <li class="pure-menu-item"><a @click="select('Lexus')" href="#" class="pure-menu-link">Lexus</a></li>
      <li class="pure-menu-item"><a @click="select('Hyundai')" href="#" class="pure-menu-link">Hyundai</a></li>
      <li class="pure-menu-item"><a @click="select('BMW')" href="#" class="pure-menu-link">BMW</a></li>
      <li class="pure-menu-item"><a @click="select('Dodge')" href="#" class="pure-menu-link">Dodge</a></li>
      </ul>
      </div>
  <ProductList :products="products" />
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Browse',
  components: {
    ProductList
  },
  data() {
    return {
      make: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.make === this.make);
    }
  },
  methods: {
    select(make) {
      this.make = make;
    }
  }
}
</script>