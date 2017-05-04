<template>
  <a-scene id="app">
    <a-assets> 
      <img id='sky' src='src/assets/daylight.png'></img>
    </a-assets>

    <a-camera>
      <a-cursor></a-cursor>
    </a-camera>

    <a-sky src='#sky'></a-sky>
    <a-plane height='10' width='10' color='green' rotation='-90 0 0'></a-plane>
    <a-plane height='10' width='10' color='gray' rotation='0 -90 0' position='5 5 0'></a-plane>
    <a-plane height='10' width='10' color='gray' rotation='0 90 0' position='-5 5 0'></a-plane>

    <wall v-for='(tag, index) in tags' v-bind:header='tag.header' font='ehh' v-bind:index='index' v-bind:side='tag.side'></wall>
  </a-scene>
</template>

<script>
import Wall from './components/Wall.vue'
export default {
  name: 'app',
  data () {
    return {
      tags: [{header: 'Wild', side: 'right'},
      ]
    }
  },
  components: {
    'wall': Wall
  }
}
</script>

<style>

</style>
