<template>
  <div class="login">
    <h3>Faça seu login para continuar</h3>
    <input type="text"  v-model="firstname" placeholder="Digite seu nome"/>
     <input type="text"  v-model="lastname" placeholder="Digite seu sobrenome"/>
    <input type="text" placeholder="Digite seu telefone" v-mask="'(##) #####-####'" v-model="phone"/>
    <button type="button" @click="showInfo">Continuar</button>
  </div>
</template>

<script>
import Vue from 'vue';
import VueMask from 'v-mask'

Vue.use(VueMask);

export default {
  name: 'Login',
  props: {
    msg: String,
    firstname: String,
  },
  data: () => ({
    firstname: '',
    lastname: '',
    phone: '',
  }),
  methods: {
    showInfo(){
      if(!this.firstname || !this.lastname || !this.phone){
        alert("Há campos não preenchidos, para continuar preencha todos os campos!")
      }else{
        alert(this.firstname + " " + this.lastname + ", " + this.phone)
      }
    }
  }
}
</script>

<style>
*{
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
.login{
  height: auto;
  margin: 0 auto;
  position: relative;
  min-width: 100%;
  padding: 20%;
  display: inline-grid;
}
input{
  margin-top: 15px;
  max-width: 100%;
  padding: 20px;
  height: 35px;
  border-radius: 4px;
  border: 1px solid rgb(255, 255, 255, 0.8);
  background-color: transparent;
  color: #fff;
}
button{
  margin-top: 15px; 
  width: 70%;
  margin-left: 15%;
  height: 35px;
  border-radius: 4px;
  border: none;
  background-color: #fff;
  color:#714b36 ;
  font-size: 16px;
}
::placeholder{
  color: #fff;
  opacity: 0.8;
}

h3{
  color: #fff;
}

</style>
