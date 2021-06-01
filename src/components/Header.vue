<template>
  <header class="cabecera">
    <img alt="Adventure time logo" src="../assets/logo.jpg" width="120" height="65"/>
    <span class="ml-4 text-lg font-bold text-green-100 md:text-xl">
      Adventure Time · Characters & Quotes!
    </span>
  </header>
</template>


<style>

.cabecera {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  background-color:  var(--bg-primary);
  font-family: "Verdana, sans-serif", sans-serif;
  color: var(--text-light);
}
.cabecera img {
  margin: 1.5rem 0;
  border-radius: 50%;
  box-shadow: 0 0 8px 1px var(--bg-light);

}
.cabecera span {
  font-size: 1.5rem;
  color: var(--text-light);
  margin: 0rem 1rem 1.5rem 1rem;
  text-shadow: 0px 0px 2px rgba(255,255,255,0.5);
}
@media (min-width:585px) {
  .cabecera span {
    font-size: 1.5rem;
    margin: 2.5rem 1rem 1.5rem 1rem;
  }
}
</style>
