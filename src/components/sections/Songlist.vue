<template>
  <div class="container">
    <div class="row mt-5 ">
      <div class="col-12 col-sm-6 col-lg-3 " v-for="(card, index) in cards" :key="index">
        <Cardlist :info="card" /> 
      </div>
    </div>
  </div>
</template>

<script>
import axios from'axios';
import Cardlist from '../commons/Cardlist.vue';

export default {
  name:"Songlist",

  components: {
    Cardlist
  },

  data() {
    return {
      cards: null,
    };
  },

  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        // handle success
        this.cards = response.data.response;
      })
      .catch(function (error) {
        // handle error
        console.log(error);
      });
  },
  
}
</script>

<style lang="scss" scoped>
img {
  width:100%;
}
</style>