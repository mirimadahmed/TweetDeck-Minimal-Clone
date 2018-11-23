<template>
  <b-container id="app" fluid v-bind:style="{ backgroundColor: getColor()}">
    <b-row>
      <b-col sm="3">
        <config-card :cols='Colomns' @lengths='saveLengths'></config-card>
        Background Color: <colorpicker :color="color" v-model="color" />
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
import colorpicker from './components/ColorPicker.vue';
export default {
  name: 'app',
  components: {
    Colomn,
    ConfigCard,
    draggable,
    colorpicker
  },
  data() {
    return {
      Colomns: ['makeschool', 'ycombinator', 'newsycombinator '],
      lengths: [],
      color: '#e6ecf0'
    };
  },
  methods: {
    saveLengths(lengths){
      this.lengths = lengths;
    },
    getColor() {
      if (localStorage.color) {
        this.color = localStorage.color;
      }
      return this.color
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
}
</style>
