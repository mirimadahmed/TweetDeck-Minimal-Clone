<template>
  <b-container id="app" fluid>
    <b-row>
      <Colomn v-for="(Colomn, i) in Colomns" :key="i"/>
    </b-row>
  </b-container>
</template>

<script>
import Colomn from './components/Colomn.vue'

export default {
  name: 'app',
  components: {
    Colomn
  },
  data() {
    return {
        Colomns: [1,2,3]
    };
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background-color: cadetblue;
}
</style>
