<template>

 <router-view></router-view>
 <router-link to="/">Home</router-link>
 <br>
 <router-link to="/AboutComponent">About</router-link>
 <br>
 <router-link to="/LoginPage">Login</router-link>
 <br>
 <router-link to="/ProfileComponent/Peter">Peter Profile Page</router-link>
 <br>
 <router-link to="/ProfileComponent/Sam">Sam Profile Page</router-link>
 
</template>

<script>
import axios from 'axios';
export default {
  name: 'App',
  data()
  {
    return{
      list:[]
      
    }
  },
  async mounted()
  {
    let result=await axios.get(" https://reqres.in/api/users?page=1")
    console.warn("api data",result.data.data);
    this.list=result.data.data;
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
  margin-top: 60px;
}
</style>
