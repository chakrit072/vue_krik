<template>
  <div id="app">
    <div id="nav">
      <Menu mode="horizontal" :theme="theme1" active-name="1">
        <MenuItem name="1" to="/">
          <Icon type="ios-paper" />
          Home
        </MenuItem>
        <MenuItem name="2" to="/about">
          <Icon type="ios-people" />
          About
        </MenuItem>
        <MenuItem name="3" to="/result">
          <Icon type="ios-stats" />
          Result
        </MenuItem>
      </Menu>
    </div>
    
    <router-view/>
   
  </div>
</template>
<script>
export default {
  data () {
    return {
      theme1: 'light'
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
</style>
