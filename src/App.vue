<template>
  <row :glutter="12" id="app">
    <column id="container">
      <newImage :url='default_image'/>
    </column  >
    <Login />
  </row>
</template>

<script>
import Login from './components/Login.vue'
import Image from './components/newImage.vue'
import default_image from './assets/texture1.jpg'
import Vue from 'vue';
import { Row, Column } from 'vue-grid-responsive'

Vue.component('row', Row);
Vue.component('column', Column);

export default {
  name: 'App',
  components: {
    Login,
    newImage : Image,
  },
  data : () => {
    return { 
      default_image
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  width: 1920px;
  margin: 0 auto;
}
#container {
  display: block;
  position: relative;
}
</style>
