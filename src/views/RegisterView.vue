<template>
    <div class="Register">
        <h1 id="title">Cree una cuenta para acceder a sus datos</h1>
        
        <form class="cuadro" method="post">
            <h2>Cree su cuenta:</h2>
            <div id="pad">
                <p1 id="user">Usuario: </p1>
                <input type="text" class = input-user v-model="nombre" placeholder="Digite su nombre">
            </div>
            <div id="pad2">
                <p1 id="clave1">Clave: </p1>
                <input type="password" pattern=".{6,}" class = input-clave v-model="clave" placeholder="Digite su clave">
            </div>
            <div id="pad3">
                <p1 id="clave2">Confirmación: </p1>
                <input type="password" pattern=".{6,}" class = input-clave v-model="clave" placeholder="Confirme su clave">
            </div>
            <div>
                <button type="submit" class = button>Registrarse</button>
            </div>
        </form>
    </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  data(){
    return {
      nombre: '',
      clave: '',
      clave2: ''
    }
  }
});
</script>

<style>
.cuadro{
    border: 1px solid #d3ced2;
    padding: 20px;
    margin: 2em 35em;
    border-radius: 5px;
}
#title{
    color: #288116;
}
.input-user{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #27264d;
  padding: 10px;
  font-size: 20px;
  height: 5px;
  align-items: center;
}
.input-clave1{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  padding: 10px;
  font-size: 20px;
  height: 5px;
  align-items: center;
}
.input-clave2{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  padding: 10px;
  font-size: 20px;
  height: 5px;
  align-items: center;
}
#user{
text-align: left;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #27264d;
  padding: 10px;
}
#clave1{
    text-align: left;
    font-size: 20px;
    padding: 20px;
}
#clave2{
    text-align: left;
    font-size: 20px;
    padding: 20px;
}
#pad{
    padding: 10px;
}
#pad2{
    padding: 10px;
}
#pad3{
    padding: 10px;
}
.button{
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    background-color: #008CBA;
}
</style>