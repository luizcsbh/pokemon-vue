<template>
  <div>
    <h2>Pokémons escolhidos</h2>
    <p v-if="favoriteListLength < maximumList">
      Preciso de ajuda <button
        class="nes-btn is-success"
        @click="startInterval"
      >
        Escolha um Pokémon
      </button>
    </p>
    <template>
      <p
        v-for="(pokemonName, index) in favorites"
        :key="index"
        class="chosen-pokemon"
      >
        <img
          src="../assets/pokeball.png"
          alt="pokeball"
        >
        {{ pokemonName }}
      </p>
    </template>
    <p v-if="favoriteListLength > 1 && favoriteListLength < maximumList">
      Você pode adicionar mais {{ maximumList - favoriteListLength }} Pokémons
    </p>
    <p v-if="favoriteListLength > 9">
      Sua lista está cheia
    </p>
    <p v-if="favoriteListLength > 9">
      Você quer <button
        class="nes-btn is-error"
        @click="emptyFavoritePokemonList"
      >
        Remover
      </button> da lista?
    </p>
    <router-link
      v-if="favoriteListLength > 0"
      class="nes-btn"
      to="/favorites"
    >
      Vizualização do Pokémons favoritos
    </router-link>
  </div>
</template>

<script>
    export default {
        name: 'SummaryFavorites',
        props: {
          pokemonList: {
            type: Array,
            required: true
          },
          favorites: {
            type: Array,
            required: true
          }
        },
        data: function() {
            return {
                maximumList: 10
            }
        },
        computed: {
            favoriteListLength() {
                return this.favorites.length
            }
        },
        methods: {
          startInterval() {
            const self = this
            const intervalID = window.setInterval(pickRandomPokemonOrClearInterval, 500)
            function pickRandomPokemonOrClearInterval() {
              if(self.favoriteListLength < self.maximumList) {
                self.pickRandomPokemon()
              } else {
                clearInterval(intervalID)
              }
            }

          },
          pickRandomPokemon() {
            const list = this.pokemonList.filter(function(pokemon){
              return !this.favorites.includes(pokemon.name)
            }, this)
            
            const number = Math.floor(Math.random() * Math.floor(list.length))
            this.$emit('addFavorite', list[number].name)
          },
          emptyFavoritePokemonList() {
            this.$emit('eraseFavoritePokemonList')
          }
        }
    }
</script>

<style scoped>
.chosen-pokemon {
    text-transform: capitalize;
}
</style>