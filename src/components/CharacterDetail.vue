<template lang="html">
  <div v-if='character'>
    <br>
    <br>
    <h3 text-align="center"><u> {{ character.name }} </u></h3>
    <p id="nickname">Nickname: {{ character.nickname }}</p>
    <p>Status: {{ character.status }}</p>
    <br>
    <p>
      <img id="character-photo" :src="character.img" height= 250px border="4"/>
    </p>
    <button v-on:click="AddToFavourite"><h3>Add Favourite Character</h3></button>
    <br>
    <br>
    <button v-on:click="DeleteFavourite"><h3>Delete Favourite Character</h3></button> 
  </div>
</template>

<script>
import{eventBus} from '../main.js';

export default {
  name: 'character-detail',
  props: ['character'],
  methods: {
    AddToFavourite(){
      eventBus.$emit('favourite-character', this.character)
    },
    DeleteFavourite(){
      eventBus.$emit('delete-character', this.character)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
