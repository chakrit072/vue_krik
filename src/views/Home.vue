<template>
  <div class="home">

    <h1 style="font-size:48px;margin:50px 0">ลงทะเบียนปฏิบัติธรรม</h1>
     
    <HelloWorld />

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
