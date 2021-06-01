<template>
  <div class="lista">
    <Tarjeta v-for="(post, index) in posts" :key="index" :post="post" />
  </div>
</template>

<script>
import Tarjeta from "./Tarjeta.vue"

export default {
  props: {
    posts: {
      type: Array,
      required: true,
      nombre: String,
    },
  },
  components: {
    Tarjeta,
  },
}
</script>

<style>
.lista {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
