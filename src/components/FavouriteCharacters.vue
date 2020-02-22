<template lang="html">

  <div>
    <br>
    <br>
    <h3><u>Favourite Characters</u></h3>
    <ul style="list-style-type:none;">
      <li v-for="(character, index) in favouritecharacters" :character="character" :key="index"><br><br>{{character.name}}<br><br><img :src="character.img" height= 110px border="3" /><hr></li>
    </ul>

  </div>
</template>

<script>

export default {
  name: 'favourite-characters',
  props: ['favouritecharacters']
}
</script>

<style lang="css" scoped>
</style>
