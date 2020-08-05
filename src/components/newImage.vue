<template>
  <div :xs="3" :md="6" :lg="12"  >
    <img :src='url' />
  </div>
</template>

<script>

export default {
  props: ['url']
}
</script>

<style >
img{
  max-width: 100%;
  height: auto;
  position: absolute;
}
</style>