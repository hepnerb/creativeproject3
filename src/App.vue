<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="/images/logo.png">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/">
        <div class="menu-item browse">
          <img src="">
          <p>Home</p>
        </div>
      </router-link>
      <router-link to="/browse">
        <div class="menu-item browse">
          <img src="">
          <p>Browse by Make</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <img src="">
          <p>My List</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <div class="footer">
  <a href="https://github.com/hepnerb/creativeproject3.git">Github Link</a>
</div>
</div>
</template>

<script>
export default {
  computed: {
    itemnumber(){
      return this.$root.$data.cart.length
    }
  },
  
}
</script>
<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
.footer {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  background-color: white;
  color: black;
  font-family: 'Courier New', Courier, monospace;
  font-size: 30px;
  text-align: center;
}
</style>