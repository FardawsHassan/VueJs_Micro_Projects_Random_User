<template>
  <UserInfo></UserInfo>
</template>

<script>
import UserInfo from './components/user.vue'

export default {
  name: 'App',
  components: {
     UserInfo
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
