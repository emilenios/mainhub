<template>
    <header class="header"> 
        <h1>TodoList</h1>
         <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
    </header>
</template>


<script>
export default {
    name: "Header"    
}
</script>

<style scoped>
    .header{
        background: rgb(71, 58, 71);
        color:antiquewhite;
        text-align: center;
        padding: 10px;

    }

    .header a{
        color: #fff;
        padding-right: 5px;

    }

</style>