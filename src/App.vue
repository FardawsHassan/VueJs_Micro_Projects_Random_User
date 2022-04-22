<template>
  <UserInfo :getdata="userdata"></UserInfo>
</template>

<script>
import UserInfo from './components/user.vue'
// import vue from 'vue'
// import axios from 'axios'
// import VueAxios from 'vue-axios'
// vue.use(VueAxios.axios)

export default {
  name: 'App',
  components: {
     UserInfo
  },
  data(){
    return{
      dataList:[],
      user: {
        name:null,
        gender:null,
        phone:null,
        cell:null,
        email:null,
        picture:null,
        dob:null,
        location:null
      }
    }
  },
  methods: {
    async getdata(){
      const res = await fetch("https://randomuser.me/api");
      const{ results } = await res.json()
      var d = results[0]

      this.user.name = d.name
      this.user.gender = d.gender
      this.user.phone = d.phone
      this.user.cell = d.cell
      this.user.email = d.email
      this.user.picture = d.picture
      this.user.dob = d.dob
      this.user.location = d.location
      console.log(this.user)
      this.dataList.push(this.user)
    },
    userdata(){
      this.getdata()
      this.getdata()
      this.getdata()
      this.getdata()
      console.log(this.dataList)
      //console.log(this.getdata().gender)
      //this.dataa.push(this.getdata())
      //console.log(this.dataa[0])
      //console.log(JSON.parse(JSON.stringify(this.dataa[0])).gender)
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
  margin-top: 70px;
}
</style>
