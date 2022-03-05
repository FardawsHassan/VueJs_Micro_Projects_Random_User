<template>
  <UserInfo :getdata="getdata"></UserInfo>
</template>

<script>
import UserInfo from './components/user.vue'

export default {
  name: 'App',
  components: {
     UserInfo
  },
  data(){
    return{
      data:null,
      userdata: null
    }
  },
  methods: {
    getdata: function(){
      console.log("hello")
      this.userdataa()
    },
    async userdataa(){
      console.log("haas")
      const res = await fetch("https://randomuser.me/api/")
      //this.userdata = res.json()
      console.log(res)
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
