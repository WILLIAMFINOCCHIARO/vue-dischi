<template>
  <div class="container">
    <div class="row text-center">
      <div class="col-12">
        <SearchBar @search="searchCard"/>
      </div>
    </div>
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
import SearchBar from '../commons/SearchBar.vue';

export default {
  name:"Songlist",

  components: {
    Cardlist,
    SearchBar
  },

  data() {
    return {
      cards: null,
      searchText: ""
    };
  },

  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        // handle success
        this.cards = response.data.response;
        this.cardsFiltered = response.data.response;
      })
      .catch(function (error) {
        // handle error
        console.log(error);
      });
  },
  methods:{
    searchCard(payload){
      this.searchText = payload;
    }

  },

  computed: {
        charactersFiltered() {
            const arrayFiltered = this.cards.filter( (elm) => {
                return elm.name.toLowerCase().includes(this.searchText.toLowerCase()); // true o false
            } );  // se è true mantengo il personaggio altrimenti lo scarto
            return arrayFiltered;
        }
    }

  
  
}

</script>

<style lang="scss" scoped>
img {
  width:100%;
}
</style>