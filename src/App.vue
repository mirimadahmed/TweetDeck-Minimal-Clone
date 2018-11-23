<template>
  <b-container id="app" fluid>
    <b-row>
      <b-col sm="3">
        <config-card :cols='Colomns' @lengths='saveLengths'></config-card>
      </b-col>
      <b-col sm="9">
        <draggable v-model="Colomns" :options="{group:'Colomns'}" element='b-row' @start="drag=true" @end="drag=false">
          <b-col v-for="(Colomn, i) in Colomns" :key="i">
            <Colomn :name='Colomn' :length='lengths[i]'/>
          </b-col>
        </draggable>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Colomn from './components/Colomn.vue'
import ConfigCard from './components/ConfigCard.vue'
import draggable from 'vuedraggable'
export default {
  name: 'app',
  components: {
    Colomn,
    ConfigCard,
    draggable
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
