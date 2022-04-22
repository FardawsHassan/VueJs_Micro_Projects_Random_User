<template>
  <UserInfo :getdata="userdata" :data="dataList"></UserInfo>
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
      dataList:[],
    }
  },
  methods: {
    async getdata(){
      const res = await fetch("https://randomuser.me/api");
      const{ results } = await res.json()
      this.dataList.push(results[0])
    },
    userdata(){
      this.emptyList()
      this.getdata()
      this.getdata()
      this.getdata()
      this.getdata()
      console.log(this.dataList)
    },
    emptyList(){
      while(this.dataList.length > 0) {
        this.dataList.pop();
      }
    }
  },
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
