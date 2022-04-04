<template>
  <div class="flexContainer">
      <img class="imagen" alt="hola" src={{producto.imagen}}>
      <span class="producto">{{producto.nombre}}</span>
      <span class="peso">Pieza de {{producto.peso}}g</span>
      <span class="precioEntero">
        <span>{{producto.precio}}€</span>
        <span> /ud.</span>
      </span>
      <button v-if="unidades < 1" class="boton" type="button" v-on="contador += 1">
        Añadir al carro
      </button>
        <div class="flexRow" v-if="unidades > 0">
          <div class="flexCompra">
            <span class="enCarro"> En carro </span>
            <span class="unidadesEnCarro">
              <span>{{contador}}</span>
              <span> ud.</span>
            </span>
          </div>
          <div class="flexBotones">
            <button class="botonAñadirUnidad" type="button" v-on="contador += 1">
              +ud
            </button>
            <button class="botonEliminarUnidad" type="button" v-on="contador -= 1">
              -ud
            </button>
          </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'ProductCard',
  props: {
    type: Object,
    default: null,
  }
}

// eslint-disable-next-line no-undef
new Vue({
  data(){
    return{
      contador: 0
    }
  }
})

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.flexContainer{
    height: 490px;
    width: 250px;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    border-style: outset;
}

.flexRow{
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: flex-start;
    margin-top: 10px;
}

.flexCompra{
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    margin-top: 10px;
}

.flexBotones{
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    align-items: flex-start;
    margin-left: 80px;
    margin-top: 20px;
}

.imagen{
    height: 250px;
    width: 250px;
}

.producto{
    margin-left: 5px;
    font-size: 26px;
}

.peso{
    margin-left: 5px;
    font-size: 18px;
    color: darkgray;
}

.boton{
    width: 100%;
    align-self: center;
}

.precioEntero{
    margin-top: 65px;
}

.enCarro{
    margin-left: 5px;
}

.unidadesCarro{
    margin-left: 5px;
}

</style>
