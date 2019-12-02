<template>
  <div id="app">
    <Header />
    
  </div>
</template>

<script>

import Header from './components/layout/Header';
export default {
  name:"app",
  components: {
    Header
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #f2faf6;
}

#nav a.router-link-exact-active {
  color: #9ef5ce;
}
</style>
