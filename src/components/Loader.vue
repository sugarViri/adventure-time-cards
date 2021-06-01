<template>
   <div>
     <slot name="loading" v-if="loaded === true">
       <Skeleto />
     </slot>
     <slot name="content" v-if="loaded === false"></slot>
   </div>
</template>

<script>
import Skeleto from './Skeleto.vue';

export default {
  name: 'Loader',
  props: {
    loaded: {
      type: Boolean,
      default: null
    }
  },
  components: {
    Skeleto
  }
}
</script>
