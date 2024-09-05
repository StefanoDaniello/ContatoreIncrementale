<template>
  <div>
    <h1>Hello</h1>
    <!-- <CardComponents :props="cardData"/> -->
     <ToDo />

  </div>
</template>

<script>
import CardComponents from './components/CradComponents.vue';
import ToDo from './components/ToDo.vue'
  export default {
    name: 'App',
    components :{
      CardComponents,
      ToDo
    },
    data(){
      return{
        cardData:[
          {name:"Gianpiertoldo",sottotitolo:"Sottopagato"},
          {name:"Gianpiertoldo",sottotitolo:"Sottopagato"},
          {name:"Gianpiertoldo",sottotitolo:"Sottopagato"},
          {name:"Gianpiertoldo",sottotitolo:"Sottopagato"}
        ]
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>
