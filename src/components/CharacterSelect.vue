<template lang="html">
  <div>
  <form>
    <br>
    <br>
    <label for="characterSelect"><h3><u>Select A Character</u></h3></label>
    <br>
    <select id="characterSelect" v-on:change="handleChange" v-model="character">
      <option v-for="(character, index) in characters" :value="character" :key="index">{{character.name}}</option>
    </select>
  </form>
  </div>

</template>

<script>
import ListItem from  './ListItem.vue';
import {eventBus} from '../main.js';

export default {
  name: 'character-select',
  data(){
    return {
      character: null
    }
  },
  props: ['characters'],
  methods: {
    handleChange() {
      eventBus.$emit('character-selected', this.character);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
