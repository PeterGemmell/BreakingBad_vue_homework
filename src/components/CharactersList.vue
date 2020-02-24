<template lang="html">
  <div>
    <label><h3>Select A Character:</h3></label>
    <br>
    <br>
    <br>
    <ul>
      <list-item v-for="(character, index) in characters" :character="character" :key="index"></list-item>
    </ul>
  </div>

</template>

<script>
import ListItem from './ListItem.vue';

export default {
  name: 'characters-list',
  props: ['characters'],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
