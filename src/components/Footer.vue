<template>
  <footer class="pie">
    <p>&copy; {{ year }} Ana MAR aka sugarViri</p>
  </footer>
</template>

<script>
export default {
  computed: {
    year() {
      return new Date().getFullYear();
    },
  },
}
</script>

<style>
.pie {
  margin-top: 3rem;
  padding: 4rem;
  background-color:  var(--bg-primary);
  color: var(--text-light);
}
</style>
