<template>
  <Header />
  <main class="global">
    <slot />
  </main>
  <Footer />
</template>

<script>
import Header from "./Header.vue"
import Footer from "./Footer.vue"

export default {
  components: {
    Header,
    Footer,
  },
}
</script>

<style>

.global {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  display: block;
}
</style>
