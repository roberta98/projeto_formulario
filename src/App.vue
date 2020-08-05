<template>
  <row :glutter="12" id="app">
    <column id="container">
      <newImage :url='default_image'/>
      <div id="form">
        <Login />
      </div>
    </column>
  </row>
</template>

<script>
import Login from './components/Login.vue'
import Image from './components/newImage.vue'
import default_image from './assets/texture1.jpg'
import Vue from 'vue';
import { Row, Column } from 'vue-grid-responsive'
import VueMask from 'v-mask'

Vue.use(VueMask);

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
      default_image,
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
#container {
  width: 1920px;
  margin: 0 auto;
  display: block;
  position: relative;
}
#form{
    width: 600px;
    background-color: #714b36;
    height: auto;
    position: relative;
    margin: 0 auto;
}

</style>
