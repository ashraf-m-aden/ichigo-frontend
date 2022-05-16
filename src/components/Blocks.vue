<template>
  <div class="container">

<!-- we first create 9 differents blocks by doing iteration, and each block
will dynamically receive a class name that represents its number. we also allocate the background-color dynamically
with the colors name of the array colors -->

    <div v-on:click="color" class="block" :class="[block]" :style=" {'background-color':colors[index]}" v-for="(block, index) in blocks" :key="index" >{{index+1}}</div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      colors: [ // array of colors name
        '#FFD700',
        '#00FFFF',
        '#7FFFD4',
        '#000000',
        '#4B0082',
        '#7FFF00',
        '#6495ED',
        '#006400',
        '#8B0000'
      ],
      blocks: [
        'b1', 'b2', 'b3', 'b4', 'b5', 'b6', 'b7', 'b8', 'b9' // this table represents the class of each block
      ]
    }
  },
  methods: {
    color () {
      this.colors = this.colors.sort((a, b) => 0.5 - Math.random())
      // everytime this function is called we shuffle the array of colors, and the blocks get a different color
    }
  }
}
</script>

<style scoped>
@import url(../assets/ichigo.css);
</style>
