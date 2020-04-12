<template>
<div>
        <img alt="Vue logo" src="../assets/logo.png">  
    <div >
        
        <h2>ID {{id}}</h2>
        <h2>ชื่อ {{name}}</h2>
        <h2>พระหัวหน้าศูนย์: {{lastname.holderName}}</h2>
        <h2>ศูนย์: {{lastname.addressName}}</h2>
        <h2>{{lastname.addressLv2}}</h2>
        <h2>เบอร์โทรศัพท์: {{lastname.telephone}}</h2>
    </div>
</div>
</template>
<script>
export default {
  props: {
      id: String
    },
    created () {
      this.$store.dispatch('setresultname', this.id)
    },
  computed:{
    routeString () {
       return this.$route.params.id
    },
    name(){
       return this.$route.query.name
    },
    lastname(){
       return this.$store.getters.getresultname     
    },
  }  
}
</script>