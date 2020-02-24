<template>
  <div>
    <h1 align="center"><u>Breaking Bad Characters</u></h1>
    <div class="main-container">
    <character-select :characters='characters'></character-select>
    <character-detail :character='selectedCharacter'></character-detail>
    <favourite-characters :favouritecharacters='favouriteCharacters'></favourite-characters>
    <!-- <quote-select :quotes='quotes'></quote-select>
    <quote-detail :quote="selectedQuote"></quote-detail> -->
   </div>
  </div>
</template>

<script>
import CharacterSelect from './components/CharacterSelect.vue';
import CharactersList from './components/CharactersList.vue';
import { eventBus } from './main.js';
import CharacterDetail from './components/CharacterDetail.vue';
import FavouriteCharacters from './components/FavouriteCharacters.vue';
// import QuotesList from './components/QuotesList.vue';
// import QuoteSelect from './components/QuoteSelect.vue';
// import QuoteDetail from './components/QuoteDetail.vue';

export default {
  name: 'app',
  data(){
    return {
    characters: [],
    favouriteCharacters: [],
    selectedCharacter: null
    // quotes: [],
    // selectedQuote: null
    };
  },
  mounted(){
    fetch('https://breakingbadapi.com/api/characters')
    .then(res => res.json())
    .then(characters => this.characters = characters)

  // mounted(){
  //   fetch('https://breakingbadapi.com/api/quotes')
  //   .then(res => res.json())
  //   .then(quotes => this.quotes = quotes)
  // }


    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character;
    }),
    eventBus.$on('favourite-character', (character) => {
      this.favouriteCharacters.push(character)
    }),
    eventBus.$on('delete-character', (character) => {
      const characterIndex = this.favouriteCharacters.indexOf(character);
      this.favouriteCharacters.splice(characterIndex, 1);
    })
    // eventBus.$on('quote-selected', (quote) => {
    //   this.selectedQuote = quote;


  },
  components: {
    "characters-list": CharactersList,
    "character-detail": CharacterDetail,
    "character-select": CharacterSelect,
    "favourite-characters": FavouriteCharacters,
    // "quotes-list": QuotesList,
    // "quote-detail": QuoteDetail,
    // "quote-select": QuoteSelect,
  }
}
</script>

<style>

  #app {
    background-color: grey;
  }

  .main-container {
  display: flex;
  justify-content: space-between;
  padding-left: 50px;
  padding-right: 230px;
  padding-top: 10px;
  border-top: solid;
  background-image: url('https://miro.medium.com/max/4000/0*vLYndMnLGloMvimd.jpeg');
  }



#list-info {
 display: block;
  }


#characterphoto {
  align-items: center;
}


</style>
