<template>

    <div class="row">

        <div v-for="(item, index) in items" :key="index" class="card" style="width: 13rem;">
            <img class="card-img-top" :src="item.phpto" alt="Card image cap">
            <div class="card-body">
              <h5 class="card-title">{{item.title}}</h5>
              <p class="card-text">{{item.price}}</p>
              <a @click="addtocard(item)" class="btn btn-primary">+ add</a>
            </div>
          </div>
      </div>


</template>

<script>
export default{
 props:['items'],
 methods:{
     addtocard(item){
         this.$emit('eventhandeler',item);
     }
 }
}
</script>
<style>
</style>