<template>
  <div class="hello">

    <Input v-model="massages" prefix="ios-contact" placeholder="Enter name" style="width: auto;margin:20px;" />  
    <i-select v-model="province" prefix="ios-home" style="width:200px;margin:20px;">
      <i-option v-for="addres in Province" :key="addres" :value="addres">{{addres}}</i-option>
    </i-select>
    
    <Button v-on:click="commit">click</Button>

    <div>
      <Row v-if="!isHidden">
        <i-Col span="8" v-for="(n,i) in names" :key="i">
          <Card :bordered="false" style="margin:20px;text-align: left">
            <p slot="title">{{province}}</p>
            <p>{{i+1}}. {{n.addressName}}</p>
            <p>หัวหน้าศูนย์: {{n.holderName}}</p>
            <p>เบอร์โทรศัพท์: 0{{n.telephone}}</p>
            <br>
            <Button ghost type="info" @click="clickedSendId(n.id)">เลือก</Button>
          </Card>
        </i-Col>
      </Row>   
    </div>
    <BackTop :height="100" :bottom="100">
        <div class="top"><Icon type="md-arrow-round-up"/></div>
    </BackTop>
    
  </div>
</template>

<script>
export default {
   data(){
    return{ 
      massages:"",
      province:"",
      isHidden: true,

 }
  },
  computed:{
  Province(){
    return  this.$store.getters.getProvince 
  },

  names(){
    return this.$store.getters.getProvinceSelected
    },

  

  },
  methods:{
    commit(){
        this.isHidden=!this.isHidden
        this.$store.dispatch('setProvinceBySelected',this.province)
        this.$store.dispatch('setlastname',this.massage) 
    },
    result(){
      this.$router.push('/Result')
    },
    clickedSendId (id) {
        this.$router.push({ path: `/result/${id}`, query: { name: this.massage } })
    },

  },
  name: 'HelloWorld',
  props: {
    massage: String,
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.top{
  padding: 10px;
  background: rgba(0, 153, 229, .7);
  color: #fff;
  text-align: center;
  border-radius: 2px;
}

</style>
