<!-- <template lang="html">
  <div>
    <li v-on:click="handleClick">{{quote.author}}</li>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'quotelist-item',
  props: ['quote'],

  methods: {
    handleClick: function(){
      eventBus.$emit('quote-selected', this.quote)
    },
  }
}
</script>

<style lang="css" scoped>
</style> -->
