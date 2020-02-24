<!-- <template lang="html">
  <div>
    <form>
      <br>
      <br>
      <label for="quoteSelect"><h3><u>Select A Character For Quotes</u></h3></label>
      <br>
      <select id="quoteSelect" v-on:change="handleChange" v-model="quote">
      <option v-for="(quote, index) in quotes" :value="quote" :key="index">{{quote.author}}</option>
     </select>
   </form>
 </div>

</template>

<script>
import QuoteListItem from './QuoteListItem.vue';
import {eventBus} from '../main.js';

export default {
  name: 'quote-select',
  data(){
    return {
      quote: null
    }
  },
  props: ['quotes'],
  methods: {
    handleChange() {
      eventBus.$emit('quote-selected', this.quote);
    }
  }
}
</script>

<style lang="css" scoped>
</style> -->
