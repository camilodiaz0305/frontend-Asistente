<template>
  <div class="home">
    <div id="Cuenta">
      <p1>Inicie sesion o registrese:</p1>
    </div>
    <div id="Sesion">
      <router-link to="/Login">Login</router-link>|
      <router-link to="/Register">Register</router-link>
    </div>
    <div>
      <img alt="Vue logo" src="../assets/sun-sun-ray-icon-transparent-free.png">
    </div>
    
    <h1>Hola Bogota</h1>
    <h1>la temperatura es {{ temperatura }}</h1>

  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default Vue.extend({
  data(){
    return {
      temperatura: 17.5
    }
  }
});
</script>

<style>
#Sesion{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: right;
  color: #27264d;
  padding: 20px;
}
#Cuenta{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: right;
  color: #09d124;
  font-weight: bold;
  padding: 30px;
}
</style>



