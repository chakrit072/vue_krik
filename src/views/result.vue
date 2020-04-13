<template>
<div>

  <Layout>
    <Content>
      <Card style="margin: 30px;">
        <Row>
          <i-Col span="12">
            <Card style="overflow: hidden; width:100%;">

            <img  src="../assets/001.jpg.jpg" width="600">  
            </Card>
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
                    <ListItem>ตำบล</ListItem>
                    <ListItem>อำเภอ</ListItem>
                    <ListItem>จังหวัด</ListItem>
                    <ListItem>ภาค</ListItem>
                    <ListItem>รหัสไปรษณีย์</ListItem>
                  </i-Col>
                  <i-Col span="18">
                    <ListItem>{{lastname.addressLv4}}</ListItem>
                    <ListItem>{{lastname.addressLv3}}</ListItem>
                    <ListItem>{{lastname.addressLv2}}</ListItem>
                    <ListItem>{{lastname.addressLv1}}</ListItem>
                    <ListItem>{{lastname.postCode}}</ListItem>
                  </i-Col>
                </List>
            </Row><br>
            <Card>
            <Row>
                <Avatar style="background-color: #87d068" icon="ios-person" size="large" />
                <p>{{name}}</p>
            </Row><br>
          
            <Row >
              <i-Col span="12">
                <h4>เริ่มปฏฺิบัติธรรม</h4>
                <DatePicker v-model="time" type="datetime" format="yyyy-MM-dd  HH:mm" placeholder="เริ่มวันที่" style="width: 200px"></DatePicker>
              </i-Col>
              <i-Col span="12">
                <h4>ระยะเวลา</h4>
                <RadioGroup v-model="type" type="button">
                  <Radio label="1 สัปดาห์"></Radio>
                  <Radio label="2 สัปดาห์"></Radio>
                  <Radio label="1 เดือน"></Radio>
                  <Radio label="3 เดือน"></Radio>
                </RadioGroup>
              </i-Col>
            </Row><br>
            <Row>
              <Button type="primary" @click="modal1 = true">ยืนยัน</Button>
              <Modal
                v-model="modal1"
                title="ยืนยันนการลงทะเบียน"
                @on-ok="ok"
                @on-cancel="cancel">
                <p></p>
                <p>{{name}} ลงทะเบียนการปฏิบัติธรรม {{type}}</p>
                <p>เริ่ม {{time}}</p>

              </Modal>
            </Row></Card>

          </i-Col>   
        </Row>
      </Card>
    </Content>
  </Layout>

</div>
</template>
<script>
export default {
   data () {
            return {
                modal1: false
            }
        },
  methods: {
      ok () {
        this.$Message.info('ลงทะเบียนเสร็จสิ้น');
        this.$router.replace('/')
      },
      cancel () {
        this.$Message.info('ยกเลิกการยืนยัน');
      }
        },
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