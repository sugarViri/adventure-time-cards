<template>
  <div class="filtro">
    <h4>Select your Character:</h4>
    <div class="contenedorSelect">
      <select v-model="nombre">
        <option
          v-for="(nombre, index) in nombres"
          :key="index"
          :value="nombre"
        >
          {{ capitalize(nombre) }}
        </option>
      </select>
    </div>
  </div>
</template>

<script>
import { computed } from "vue"
/* import sectionsData from "./nombres" */

export default {
  props: {
    modelValue: String,
    nombres: Array,
  },
  setup(props, { emit }) {
    const nombre = computed({
      get: () => props.modelValue,
      set: value => emit("update:modelValue", value),
    })
    return {
      nombre,
    }
  },
  data() {
    return {
    }
  },
  methods: {
    capitalize(value) {
      if (!value) return ""
      value = value.toString()
      return value.charAt(0).toUpperCase() + value.slice(1);
    },
  },
}
</script>

<style>
.filtro {
  padding-top: 0.5rem;
  width: 100%;
}
.filtro h4 {
  font-family: "Verdana, sans-serif", sans-serif;
  font-size: 1.2rem;
  color: var(--text-regular);
  margin-bottom: 1.2rem;
}

.filtro select {
  display: block;
  font-size: 16px;
  font-family: 'Verdana', sans-serif;
  font-weight: 400;
  color: var(--text-regular);
  line-height: 1.3;
  padding: .4em 1.4em .3em .8em;
  width: 210px;
  max-width: 100%;
  box-sizing: border-box;
  margin: 20px auto 10px auto;
  border: 1px solid #cfcacf;
  box-shadow: 0 1px 0 1px rgba(0,0,0,.03);
  border-radius: .3em;
  -moz-appearance: none;
  -webkit-appearance: none;
  appearance: none;
  background-color: var(--bg-light);
  background-image: url('data:image/svg+xml;charset=US-ASCII,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22292.4%22%20height%3D%22292.4%22%3E%3Cpath%20fill%3D%22%23e979f0%22%20d%3D%22M287%2069.4a17.6%2017.6%200%200%200-13-5.4H18.4c-5%200-9.3%201.8-12.9%205.4A17.6%2017.6%200%200%200%200%2082.2c0%205%201.8%209.3%205.4%2012.9l128%20127.9c3.6%203.6%207.8%205.4%2012.8%205.4s9.2-1.8%2012.8-5.4L287%2095c3.5-3.5%205.4-7.8%205.4-12.8%200-5-1.9-9.2-5.5-12.8z%22%2F%3E%3C%2Fsvg%3E' ),
    linear-gradient(to bottom, #ffffff 0%,#f7f7f7 100%);
  background-repeat: no-repeat, repeat;
  background-position: right .7em top 50%, 0 0;
  background-size: .65em auto, 100%;
}
select::-ms-expand {
  display: none;
}
select:hover {
  border-color: #f2a0f2;
}
select:focus {
  border-color: #c4bec4;
  box-shadow: 0 0 1px 3px rgba(233, 121, 240, .3);
  box-shadow: 0 0 0 3px -moz-mac-focusing;
  color: #222;
  outline: none;
}
select option {
  font-weight:normal;
}
select option:checked {
background-color: rgba(233, 121, 240, .3);
}

</style>
