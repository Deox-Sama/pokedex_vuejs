<template>
  <div class="container">
    <PokemonSearch @searchPokemonEmit="searchPokemon" />
    <PokemonDetail @event_from_child2="closeDetail" :visible="visible" :pokemonUrl="pokemonUrl" />
    <PokemonList @event_from_child="dataPkmList" :search="search" />
  </div>
</template>

<script>
import PokemonDetail from "../components/PokemonDetail.vue";
import PokemonList from "../components/PokemonList.vue";
import PokemonSearch from "../components/PokemonSearch.vue";

export default {
  data: function () {
    return{
      visible: false,
      pokemonUrl:"",
      search:"",
      
      
    }},
  
  

  components: {
    PokemonDetail,
    PokemonList,
    PokemonSearch,
  },

  methods:{
    dataPkmList(pokemonUrl){
      this.pokemonUrl = pokemonUrl
      this.visible=true
    },

    dataPkmImg(pokImg){
      this.pokImg = pokImg
    },

    closeDetail(){
      this.visible=false
    },

    searchPokemon(search) {
      this.search = search
    }
  }
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 10px;
  width: calc(100% - 20px);
  min-height: calc(100vh - 20px);
  //background: radial-gradient(#ffbf0b, #e20000);

  font-family: "Acme", arial;
  font-size: 1rem;
  font-weight: normal;
}

h1 {
  color: #efefef;
}
</style>