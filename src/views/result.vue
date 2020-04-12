<template>
<div>
  <Layout>
    <Content>
      <Card style="margin: 30px;">
    <Row>
        <i-Col span="12">
        <img alt="Vue logo" src="../assets/logo.png">  
        </i-Col>
        <i-Col span="12">
          <Row>
          <List header="ข้อมูลศูนย์ปฏิบัติธรรม" footer="" border size="small">
            <i-Col span="6">
              <ListItem>ศูนย์</ListItem>
              <ListItem>พระหัวหน้าศูนย์</ListItem>
              <ListItem>เบอร์โทรศัพท์</ListItem>
            </i-Col>
            <i-Col span="18">
              <ListItem>{{lastname.addressName}}</ListItem>
              <ListItem>{{lastname.holderName}}</ListItem>
              <ListItem>{{lastname.telephone}}</ListItem>
            </i-Col>
          </List></Row><br>
          <Row>
            <List header="ที่อยู่" footer="" border size="small">
              <i-Col span="6">
              <ListItem>ภาค</ListItem>
              <ListItem>ตำบล</ListItem>
              <ListItem>อำเภอ</ListItem>
              <ListItem>จังหวัด</ListItem>
              <ListItem>รหัสไปรษณีย์</ListItem>
            </i-Col>
            <i-Col span="18">
              <ListItem>{{lastname.addressLv1}}</ListItem>
              <ListItem>{{lastname.addressLv2}}</ListItem>
              <ListItem>{{lastname.addressLv3}}</ListItem>
              <ListItem>{{lastname.addressLv4}}</ListItem>
              <ListItem>{{lastname.postCode}}</ListItem>
            </i-Col>
          </List></Row>
          
          <div >
            <i-Col>
              <h2></h2>
              <DatePicker type="date" placeholder="Select date" style="width: 200px"></DatePicker>
            </i-Col>
            <i-Col>
              <RadioGroup v-model="button1" type="button">
                <Radio label="1 สัปดาห์"></Radio>
                <Radio label="2 สัปดาห์"></Radio>
                <Radio label="1 เดือน"></Radio>
                <Radio label="3 เดือน"></Radio>
              </RadioGroup>
            </i-Col>
            
            
          </div>   
        </i-Col>
    </Row>
    </Card>
    </Content>
  </Layout>
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