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
      <img alt="Vue logo" src="../assets/sun-sun-ray-icon-transparent-free.png" class="logo">
    </div>
    <form class="cuadro" method="post">
      <h1 class="bienvenida">Bienvenido a nuestra página</h1>
      <h1>la temperatura es {{ temperatura }}</h1>
    </form>
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
.home{
  background-color: #78729e42;
  padding: 18px;
}
.bienvenida{
  color: #16814f;
}
.cuadro {
  border: 1px solid #c2bdc1;
  padding: 2px;
  margin: 2em 36em;
  border-radius: 3px;
}
.logo{
  height: 300px;
  width: 300px;
}
#Sesion{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: right;
  color: #27264d;
  padding-right: 50px;
  font-size: 20px;
}
#Cuenta{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: right;
  color: #119e248a;
  font-weight: bold;
  padding-right: 50px;
  padding-bottom: 10px;
  font-size: 20px;
}
</style>



