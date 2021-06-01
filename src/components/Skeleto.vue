<template>
  <div class="contenedorSkeleto">
    <div class="cajaSkeleto">
      <div class="cajaNombre"></div>
      <svg viewBox="0 0 250 290" version="1.1"
       xmlns="http://www.w3.org/2000/svg">
        <circle fill="hsla(218, 92%, 93%, 1)" cx="120" cy="190" r="100"/>
      </svg>
      <div class="cajaBio"></div>
      <div class="cajaBio"></div>
      <div class="cajaBio"></div>
      <div class="cajaInfo"></div>
    </div>
    <div class="cajaSkeleto">
      <div class="cajaNombre"></div>
      <svg viewBox="0 0 250 290" version="1.1"
       xmlns="http://www.w3.org/2000/svg">
        <circle fill="hsla(218, 92%, 93%, 1)" cx="120" cy="190" r="100"/>
      </svg>
      <div class="cajaBio"></div>
      <div class="cajaBio"></div>
      <div class="cajaBio"></div>
      <div class="cajaInfo"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Skeleto',
}
</script>

<style>
.contenedorSkeleto {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.cajaSkeleto {
  margin: 2rem 1rem 0 1rem;
  width: 90%;
  height: 1050px;
  background-color: hsla(218, 92%, 99%, 1);
  border-radius: 1rem;
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
  position: relative;
  overflow: hidden;
}
.cajaSkeleto .cajaNombre{
  width: 100%;
  position: absolute;
  top:0;
  padding: 2.5rem 0;
  margin: 0;
  background-color:  hsla(218, 92%, 93%, 1);
  border-radius: 1rem 1rem 0 0;
}
.cajaSkeleto svg {
  width: 300px;
}
.cajaSkeleto .cajaBio {
  width: 230px;
  height: 30px;
  margin: 1.5rem auto;
  background-color: hsla(218, 92%, 93%, 1);
}
.cajaSkeleto .cajaInfo {
  width: 100%;
  position: absolute;
  top: 570px;
  bottom:0;
  padding: 23rem 0;
  background-color: hsla(218, 92%, 93%, 1);
  border-radius: 0 0 1rem 1rem;
  border-top: 30px solid hsla(218, 92%, 91%, 1);
}
.cajaSkeleto::after {
  content: '';
  position: absolute;
  opacity: 0.5;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  transform: translateX(-100%);
  animation: brilli 1.6s infinite;
  background-color: hsla(218, 30%, 76%, 0.75);
  background-image: linear-gradient(to right,
  hsla(218, 16%, 75%, 0.75) 0,
  hsla(218, 20%, 71%, 0.62) 20%,
  hsla(218, 30%, 76%, 0.75) 60%,
  hsla(218, 35%, 52%, 0.61));
  background-image: -webkit-linear-gradient(left, hsla(218, 16%, 75%, 0.75) 0,
  hsla(218, 20%, 71%, 0.62) 20%,
  hsla(218, 30%, 76%, 0.75) 60%,
  hsla(218, 35%, 52%, 0.61));
  background-image: -moz-linear-gradient(left, hsla(218, 16%, 75%, 0.75) 0,
  hsla(218, 20%, 71%, 0.62) 20%,
  hsla(218, 30%, 76%, 0.75) 60%,
  hsla(218, 35%, 52%, 0.61));
  background-image: -o-linear-gradient(left, hsla(218, 16%, 75%, 0.75) 0,
  hsla(218, 20%, 71%, 0.62) 20%,
  hsla(218, 30%, 76%, 0.75) 60%,
  hsla(218, 35%, 52%, 0.61));
}
@keyframes brilli {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(100%);
  }
}
@media (min-width: 600px) {
  .cajaSkeleto {
    width: 460px;
  }
}
@media (min-width: 760px) {
  .cajaSkeleto {
    margin: 2rem 1rem 1rem 1rem;
  }
  .cajaSkeleto .cajaBio {
    width: 290px;
  }
}
</style>
