<template>
  <h1>{{title}}</h1>
  <img src="../images/starpc.jpg" alt="background">
</template>

<script>
import { ref } from '@vue/reactivity';
export default {
  name: 'ToHome',
  setup() {
    const title = ref('Home')
    return {title}
  }
}
</script>

<style>
  img {
    border: 0;
    padding: 0; 
    min-height: 100%;
    background-position: center;
    background-size: cover;
  }
</style>