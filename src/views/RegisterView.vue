<template>
    <div class="Register">
        <h1 id="title">Cree una cuenta para acceder a sus datos</h1>

        <form class="cuadro" method="post">
            <h2>Cree su cuenta:</h2>
            <div id="pad">
                <p1 id="user">Usuario: </p1>
                <input type="text" class=input-user v-model="nombre" placeholder="Digite su nombre">
            </div>
            <div id="pad2">
                <p1 id="clave1">Clave: </p1>
                <input type="password" pattern=".{6,}" class=input-clave1 v-model="clave" placeholder="Digite su clave">
            </div>
            <div id="pad3">
                <p1 id="clave2">Confirme: </p1>
                <input type="password" pattern=".{6,}" class=input-clave2 v-model="clave2" placeholder="Confirme su clave">
            </div>
            <div v-if="clave==clave2">
                <p1 id="exito">Las claves coinciden!</p1>
            </div>
            <div v-else>
                <p1 id="falla">Las claves son distintas!</p1>
            </div>
            <div>
                <button id="miBoton" type="submit" class=button v-on:click="send()">Registrarse</button>
            </div>
        </form>
    </div>
</template>

<script>
import axios from 'axios'

//let botons = document.getElementById('miBoton');
//botons.setAttribute('disabled', true);

export default {
    data() {
        return {
            nombre: "",
            clave: "",
            clave2: ""
        }
    },
    mounted: function () {
        let vue = this.axios.get('http://localhost:3100/register')
        .then(function(response) {
            // handle success
            console.log(response.data[0]);
            var datos = response.data[0]
            vue.direccion = datos.address_1
            vue.nombre = datos.name
        })
        .catch(function(error) {
            // handle error
            console.log(error);
        })
    },
    methods:{
        send(){
            var payload = {
                user: this.nombre,
                pass: this.clave
            }
            axios.post('http://localhost:3100/register',payload)
            alert("Envio al back correcto")
        }
    }
}
</script>

<style>

#title {
    color: #288116;
}
#exito {
    color: #288116;
    font-size: 15px;
}
#falla{
    color: #ff0000;
}
.input-user {
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

.input-clave1 {
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

.input-clave2 {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #000000;
    padding: 10px;
    font-size: 20px;
    height: 5px;
    vertical-align: auto;
}

#user {
    font-size: 20px;
    text-align: left;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: left;
    color: #27264d;
    padding: 10px;
}

#clave1 {
    text-align: left;
    font-size: 20px;
    padding: 20px;
}

#clave2 {
    vertical-align: auto;
    font-size: 20px;
    padding: 5px;
}

.cuadro {
    border: 1px solid #d3ced2;
    padding: 2px;
    margin: 2em 36em;
    border-radius: 3px;
}

#pad {
    padding: 10px;
}

#pad2 {
    padding: 10px;
}

#pad3 {
    padding: 10px;
}

.button {
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 1px;
    cursor: pointer;
    background-color: #008CBA;
}
</style>