<template>
  <b-container id="app" fluid>
    <b-row>
      <b-col sm="2">
        <config-card></config-card>
      </b-col>
      <b-col sm="10">
        <b-row>
          <Colomn v-for="(Colomn, i) in Colomns" :key="i" :name='Colomn'/>
        </b-row>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Colomn from './components/Colomn.vue'
import ConfigCard from './components/ConfigCard.vue'
export default {
  name: 'app',
  components: {
    Colomn,
    ConfigCard
  },
  data() {
    return {
        Colomns: ['makeschool', 'ycombinator', 'newsycombinator ']
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
