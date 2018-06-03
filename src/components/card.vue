<template>

    <ul class="list-group">
            <li class="list-group-item">
            <span class="item-name">name</span>
            <span class="item-price float-right">price</span>
            </li>
            <li v-for="(item, index) in items" :key="index" class="list-group-item">
            <span class="item-name">{{item.title}}</span>
            <button class="btn btn-danger" @click="remove(index)">-</button>
            <span class="item-price float-right">{{item.price}}</span>

            </li>
            <li class="list-group-item">
            <span class="item-name">total</span>
            <span class="item-price float-right">${{ totalprice }}</span>
            </li>
          </ul>
</template>

<script>
export default{
  props:['items'],
  computed:{
    totalprice(){
      var total=0
      this.items.forEach(item =>{
        total +=parseFloat(item.price)
      })
      return total
    }
  },
  methods:{
    remove(index){
      this.$emit('removeHandler', index)
    }
  }

}
</script>
<style>
</style>