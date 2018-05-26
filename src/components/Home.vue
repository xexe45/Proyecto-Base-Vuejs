<template>
  <div>
   
    <form @submit.prevent="nuevo">
      <input type="text" v-model="list">
      <button type="submit">Agregar</button>
    </form>
    <items :lists="lists"></items>
  </div>
</template>

<script>
import items from './Items';
export default {
    name: 'Home',
    components: {items},
    created(){
         EventBus.$on('itemRemove', (index) => {
           this.lists.splice(index,1);
         });
    },
    data(){
      return{
        list:null,
        editar: false,
        lists: [
          {name: 'Cesar'},
          {name: 'Vuejs'},
          {name: 'Angular'}
        ]
      }
    },
    methods:{
      nuevo(){
        
        this.lists.push({name: this.list});
        this.list = null;
      },
     
      
    }
}
</script>

<style>

</style>
