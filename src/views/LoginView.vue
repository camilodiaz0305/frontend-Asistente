<template>
    <div class="login">
        <h1 id="title">Entre y conozca nuestros servicios!!</h1>
        <form class="cuadro" method="post">
            <h2>Digite su nombre de usuario y clave</h2>
            <div id="pad">
                <p1 id="user">Usuario: </p1>
                <input type="text" class=input-user v-model="nombre" placeholder="Digite su nombre">
            </div>

            <div id="pad2">
                <p1 id="clave">Clave: </p1>
                <input type="password" pattern=".{8,}" class=input-clave v-model="password" placeholder="Digite su clave">
                <i :class="eyeIconClass" @click="togglePasswordVisibility"></i>
            </div>

            <div>
                <button type="submit" class=button>Ingresar</button>
            </div>
        </form>
    </div>
</template>

<script>
import axios from 'axios'


export default {

    data() {
        return {
            nombre: "",
            password: "",
            showPassword: false
        }
    },
    mounted: function () {
        let vue = this.axios.get('http://localhost:3100/login')
            .then(function (response) {
                // handle success
                console.log(response.data[0]);
                var datos = response.data[0]
                vue.direccion = datos.address_1
                vue.nombre = datos.name
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
    },
    computed: {
        eyeIconClass() {
            return this.showPassword ? 'Hide' : 'Show';
        }
    },
    methods: {
        send() {
            var payload = {
                user: this.nombre,
                pass: this.password
            }
            axios.post('http://localhost:3100/login',payload)
            alert("Envio al back correcto")
        },
        togglePasswordVisibility() {
            this.showPassword = !this.showPassword;
        }
    }
}
</script>

<style>
.cuadro {
    border: 1px solid #d3ced2;
    padding: 20px;
    margin: 2em 35em;
    text-align: center;
    border-radius: 5px;
}

#title {
    color: #288116;
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
}

.input-clave {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #27264d;
    padding: 10px;
    font-size: 20px;
    height: 5px;
}

#user {
    font-size: 20px;
    padding: 20px;
}

#clave {
    font-size: 20px;
    padding: 20px;
}

#pad {
    padding: 10px;
}

#pad2 {
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
    margin: 4px 2px;
    cursor: pointer;
    background-color: #008CBA;
}</style>