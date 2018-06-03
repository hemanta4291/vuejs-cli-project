<template>
  <div id="app">
      <Navbar @searchHnamder="search" ></Navbar>


  <div class="container">

    <div class="row">

    <div class="col-sm-9">

      <Inventory @eventhandeler="addnewcard" :items="items"></Inventory>

    </div>

    <div class="col-sm-3">

    <card @removeHandler="removeitem" :items="card"></card>

    </div>

    </div>

  </div>



  </div>
</template>
   
<script>

import Navbar from './components/Navbar'
import Inventory from './components/Inventory'
import card from './components/card'
import data from './data.js'
export default {
  name: 'App',
  components:{
    Navbar,
    Inventory,
    card
  },
  data(){
    return{
      items:[],
      card:[
      ]
    }
  },
  mounted (){
    this.items=data
  },
  methods:{
    addnewcard(item){
      this.card.push(item);
    },
    removeitem(index){
      this.card.splice(index, 1)
    },
    search(keyword){
      this.items= data.filter(item =>{
        return item.title.toLowerCase().indexOf(keyword.toLowerCase()) !==-1
      })
    }
  }
}
</script>

<style>

</style>
