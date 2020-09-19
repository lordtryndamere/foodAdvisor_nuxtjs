<template>
    <div>
    <p>  {{message}} </p>
    <p v-show="true"> Se muestra si es true </p>
    <p v-if="message.length > 1"> Se muestra si es mayor 1 </p>
    <p v-else> Se muestro si es igual o menor a 1 </p>
   <label> Nombre: </label> <br/>
   <input v-model="nombre"   type="text"/> <br/>
    {{ nombre }}  <br/>
    <button v-on:click="saludo"  class="button is-info" > Cambiar nombre a las tarjetas</button>
   
    <div  class="container-cards" >

        <div  :key="item.name"  v-for="(item) in data">
        <RestaurantCard  v-bind:name = "item.name" v-bind:category= "item.category" v-bind:likes= "item.likes" v-bind:description="item.descripcion" v-bind:slugs="item.slugs" />    
        </div>
    </div>



    </div>

</template>
<script>
import RestaurantCard from '../components/RestaurantCard'
export default {
    components:{
        RestaurantCard
    },
    data(){
        return {
            message:"Como seria",
            items:[1,2,3,4,5,6],
            data :[{name:"Restaurante de antioquia",category:"PESCADERIA",likes:3,descripcion:"Restaurante de pescaderia",slugs:"restaurant-name"},{name:"Restaurante de bogota",category:"MONDONGO",likes:3,descripcion:"Restaurante de MONDONGO",slugs:"restaurant-name"},{name:"Restaurante de cucuta",category:"HORMIGA",likes:3,descripcion:"Restaurante de HORMIGAS",slugs:"restaurant-name"}],
            nombre: ''
        }
    },
    methods:{
        saludo(){
            console.log(this.nombre);
        }
    }
}
</script>

<style scoped>
.container-cards{
    width: 100%;
    padding: 20px;
}
</style>