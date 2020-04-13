<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
     <h2 >Your name: {{massages}}</h2>
     <!-- <h2 >Selected:{{lastname.holderName}}</h2> -->
    <input v-model="massages" type="text" placeholder="your name" >
    <HelloWorld @lastname="name" :massage="massages"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  data(){
    return{
      massages:"",
      name_l:""
    }
  },
  methods:{
    name(value){
      this.name_l=value
    }
  },
  // computed:{
  //   lastname(){
  //     return this.$store.getters.getlastname
  //   }
  // },
  name: 'Home',
  components: {
    HelloWorld

  }
}
</script>
