<template>
  <div>
       <ul>
      <li v-for="(list, index) in lists" :key="list.name">
        {{ list.name }}
        <span><button type="button" @click="remover(index)">Remover</button></span>
        
      </li>
    </ul>
  </div>
</template>

<script>
export default {
    props: ['lists'],
    methods:{
        remover(index){
            EventBus.$emit('itemRemove', index);
        }
    }
}
</script>

<style>

</style>
