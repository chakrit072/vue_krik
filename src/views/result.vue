<template>
<div>
        <img alt="Vue logo" src="../assets/logo.png">  
    <div >
        
        <h2>ชื่อ {{lastname.namef}}</h2>
        <h2>ฉายา {{lastname.lastname}}</h2>
        <h2>ศูนย์ {{lastname.addressName}}</h2>
        <h2>{{lastname.addressLv2}}</h2>
    </div>
</div>
</template>
<script>
export default {
  computed:{
    lastname(){
       return this.$store.getters.getlastname     
    },
  }  
}
</script>