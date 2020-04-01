<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <!-- <router-view/> -->
    <h1 id="wep">{{namewep}}</h1>
    <h2>Your name {{massages}}</h2>
    <input v-model="massages" type="text">
    <button v-on:click="isHidden=!isHidden">click</button>
    <button v-on:click="alert()">alert</button>
    <h2 v-if="!isHidden" id="alert">Hello {{massages}}!</h2>
  </div>


</template>
<script>
export default {
  data(){
    return{
      namewep:"!WELCOME!",
      massages:"",
      isHidden: true

    }
  },
  methods:{
    alert: function(){
      return alert('Hello '+this.massages)
    }
  }
  
}

</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
#wep{
  color: blue;
}
#alert{
  color: red;
}
</style>
