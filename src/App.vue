<template>
  <Layout>
    <Filtro v-model="nombre" v-on:update="filtroNombre" :nombres="nombres"/>
    <Loader :loaded="loading">
      <template v-slot:loading>
      </template>
      <template v-slot:content v-if="loading === false">
        <Lista :posts="filtroNombre" />
      </template>
    </Loader>
  </Layout>
</template>

<script>
import Layout from "./components/Layout.vue";
import Filtro from "./components/Filtro.vue";
import Lista from "./components/Lista.vue";
import Loader from './components/Loader.vue';
import axios from "axios";

export default {
  components: {
    Layout,
    Filtro,
    Lista,
    Loader,
  },
  data() {
    return {
      nombre: "All",
      posts: [],
      data: null,
      error: null,
      loading: true,
    }
  },
  computed: {
    filtroNombre() {
      let filtro = this.nombre;
      return this.posts.filter(function(el) {
        if (filtro === "All") {
          return el;
        } else {
          return el.displayName.indexOf(filtro) !== -1;
        }
      });
    },
    nombres() {
      let nombresLista = this.posts.map(function(obj) {
        let soloNombres = {};
        soloNombres[obj.displayName] = obj.displayName;
        return soloNombres[obj.displayName];
      });
      nombresLista.unshift("All");
      return nombresLista;
    },
    visitado() {
       if ((PerformanceNavigation.TYPE_RELOAD) ||
        performance
          .getEntriesByType('navigation')
          .map((nav) => nav.type)
          .includes('reload')) {
        return true;
      } else {
        return false;
      }
    },
  },
  methods: {
    fetchInfo() {
      axios
      .get('https://adventure-time-api.herokuapp.com/api/v1/characters')
      .then(response => this.posts = response.data.map(post => ({
          slug: post.slug,
          displayName: post.displayName,
          fullName: post.fullName,
          species: post.species,
          sex: post.sex,
          quotes: post.quotes,
          sprite: post.sprite,
      })))
      .then(x => {
        if (this.visitado) {
          setTimeout(() => {
            this.loading = false;
          }, 1300)
        } else {
          this.loading = false;
        }
      })
      .catch(error => {
          if (err.response) {
            console.log("Error de Servidor:", err);
          } else if (err.request) {
            console.log("Error de Red:", err);
          } else {
            console.log("Error de Cliente:", err);
          }
      })
    },
  },
  async mounted() {
    this.fetchInfo();
  },
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
