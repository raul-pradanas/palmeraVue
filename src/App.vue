<script>
import ProductCard from './components/ProductCard.vue'


  const listaProductos = [
    {
      id:1,
      nombre: "palmera",
      peso: 425,
      precio: 1.75,
      imagen: "https://prod-mercadona.imgix.net/images/5e949a6f64b52be230b8f1084156dcd9.jpg?fit=crop&h=300&w=300",
    },
    {
      id:2,
      nombre: "palmera2",
      peso: 425,
      precio: 1.75,
      imagen: "https://prod-mercadona.imgix.net/images/5e949a6f64b52be230b8f1084156dcd9.jpg?fit=crop&h=300&w=300",
    }
  ];

  // eslint-disable-next-line no-undef
  new Vue({
    data(){
      return listaProductos
    }
  })

export default {
  name: 'App',
  components: {
    ProductCard
  }
}
</script>

<template>
  <product-card v-for="producto in listaProductos" :key="producto.id" :producto = "producto"/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
