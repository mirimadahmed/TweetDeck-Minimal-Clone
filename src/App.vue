<template>
  <b-container id="app" fluid>
    <b-row>
      <b-col sm="3">
        <config-card :cols='Colomns' @lengths='saveLengths'></config-card>
      </b-col>
      <b-col sm="9">
        <b-row>
          <Colomn v-for="(Colomn, i) in Colomns" :key="i" :name='Colomn' :length='lengths[i]'/>
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
      Colomns: ['makeschool', 'ycombinator', 'newsycombinator '],
      lengths: []
    };
  },
  methods: {
    saveLengths(lengths){
      this.lengths = lengths;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background-color: #e6ecf0;
}
</style>
