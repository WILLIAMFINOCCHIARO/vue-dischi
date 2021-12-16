<template>
  <div class="card my-2 " >
  <img :src="info.poster" class="card-img-top w-50 " alt="info.author">
  <div class="card-body">
    <h1>{{info.title}}</h1>
    <div class="card-text w-50">{{info.author}} </div>
    <div class="card-text w-50">{{info.year}} </div>
  </div>
</div>
  
</template>

<script>


export default {
  name:"Cardlist",
  props: {
    info:Object
  }
}
</script>


<style lang="scss" scoped>

</style>