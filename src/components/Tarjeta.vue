<template>
  <section class="tarjeta">
    <h2>{{ post.displayName }}</h2>
    <div class="imagen">
      <img
        :src="post.sprite"
        :alt="post.fullName"
        height="auto"
        width="auto" 
      />
    </div>
    <div class="contenedorBio">
      <div class="datosBio">
        <div>
          <span>Name:</span><p>{{ post.fullName }}</p>
          <span>Species:</span><p>{{ post.species }}</p>
          <span>Sex:</span><p>{{ post.sex }}</p>
        </div>
      </div>
    </div>
    <div class="infoFrases">
      <p v-for="(quote, index) in post.quotes" :key="index" :post="post">
        "{{ post.quotes[index] }}"
      </p>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
    nombre: String,
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display&display=swap');
.tarjeta {
  margin: 2rem 1rem 0 1rem;
  width: 90%;
  background-color: var(--bg-secondary);
  border-radius: 1rem;
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}
.tarjeta >h2 {
  padding-top: 2rem;
  padding-bottom: 1.5rem;
  margin: 0;
  color: var(--text-dark);
  background-color: var(--bg-primary-light);
  border-radius: 1rem 1rem 0 0;
}
.imagen {
  background-color: var(--bg-light);
}
.imagen img {
  background-color: var(--bg-primary);
  border-radius: 50%;
  margin: 1.5rem 0;
  width: 250px;
  height: 250px;
}
.contenedorBio {
  width: 100%;
  background-color: var(--bg-light);
  border-bottom: 30px solid var(--bg-accent);
  box-shadow: 0px -10px 5px var(--bg-light);
}
.datosBio {
  margin: 0 auto 2.5rem auto;
  font-size: 1.2rem;
  width: 230px;
  background-color: var(--bg-light);
  color: var(--text-regular);
  min-height: 151px;
  text-shadow: 0px 0px 1px rgba(0,0,0,0.6);
}
.datosBio >div {
  width: 100%;
}
.datosBio p {
  text-align: right;
  padding-left: 20%;
  margin-top: 0;
}
.datosBio span {
  float: left;
  display: inline;
  font-weight: bold;
}
.infoFrases {
  padding: 1.5rem 2rem 2rem 2rem;
}
.infoFrases p {
  font-family: 'Playfair Display', serif;
  color: var(--text-dark);
  font-size: 1.3rem;
  text-shadow: 0px 0px 1px rgba(0,0,0,0.6);

}
@media (min-width: 600px) {
  .tarjeta {
    width: 470px;
  }
  .datosBio {
    width: 300px;
  }
}
@media (min-width: 760px) {
  .tarjeta {
    margin: 2rem 1rem 1rem 1rem;
  }
}
</style>
