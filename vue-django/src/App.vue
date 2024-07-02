<template>
  <div class="container">
      
    <h2 class="text-primary">Eventos</h2>    
    <h6>Botones</h6>
    <button class="btn btn-primary" v-on:click="$event => hacerclick('Hizo click el triple hujueputa azul')">Hacer click aquí</button>
    <button class="btn btn-success" @click="$event => hacerclick('Hizo click el triple hujueputa verde')">Hacer click aquí</button>
    <hr>
    <h6>MODIFICADORES</h6>
    <button class="btn btn-warning" @click="$event => queBotonPresiono('Presionaste el botón izquierdo')">Izquierda</button>
    <button class="btn btn-info" @click.middle="$event => queBotonPresiono('Presionaste el botón del medio')">Central</button>
    <button class="btn btn-danger" @click.right.prevent="$event => queBotonPresiono('Presionaste el botón derecho')">Derecha</button>
    
    <h6>REACTIVIDAD</h6>
    <p>Variable "prueba" es {{prueba}} </p>
    <button class="btn btn-sm btn-success" @click="variablePrueba">La prueba es: {{ prueba1 }} </button>
    <button class="btn btn-sm btn-warning" @click="variablePruebaDes">La prueba es: {{ prueba2 }} </button>
    <br>

    <h5 class="btn btn-sm">Resultado: {{ product }}</h5>

  </div>


</template>

<script setup> 
  import {ref, computed} from 'vue';
  let prueba1 = ref(0);
  let prueba2 = ref(0);
  
  const variablePrueba = () => {
    prueba1.value++;
    console.log(prueba1)
  }
  
  const variablePruebaDes = () => {
    prueba2.value--;
    console.log(prueba2) 
  }
  
  const hacerclick = (mensaje) => {
   console.log(mensaje);
  }
  
  const queBotonPresiono = (mensaje) => {
    console.log(mensaje);
  }
  const product = computed(() => {
    return prueba1.value * prueba2.value;
  })

  const paises = [
    {bandera: "link",
      pais: "Colombia",
      capital: "Bogotá"
    },
    {bandera: "link",
      pais: "Ecuador",
      capital: "Quito"
    },
    {bandera: "link",
      pais: "Italia",
      capital: "Roma"
    },
    {bandera: "link",
      pais: "Japón",
      capital: "Tokio"
    },

  ]
  
</script>
<style>
  #app {
    font-family: Arial, Helvetica, sans-serif;
    -moz-osx-font-smoothing: grayscale;
    -webkit-osx-font-smoothing: antialiased;  }  
</style>