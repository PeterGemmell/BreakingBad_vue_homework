<template lang="html">
  <div>
    <li v-on:click="handleClick">{{character.name}}</li>
    <button v-on:click="handleClickFavourite"> Add To Favourites</button>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'list-item',
  props: ['character'],

  methods: {
    handleClick: function(){
      eventBus.$emit('character-selected', this.character)
    },
    handleClickFavourite: function(){
      eventBus.$emit('favourite-characters', this.character)
    }
  },
}
</script>

<style lang="css" scoped>
</style>
