<template>
  <div class="background">
    <Pokedex :pokemons="pokemons" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      pokemons: [],
    };
  },
  methods: {
    getPokemons() {
      this.pokemons = [];
      fetch(
        `https://raw.githubusercontent.com/fanzeyi/pokemon.json/master/pokedex.json`
      )
        .then((response) => response.json())
        .then((data) => {
          this.pokemons = data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
    test() {
      this.getPokemons();
    },
  },
  mounted() {
    this.getPokemons();
  },
};
</script>

<style scoped>
.background {
  background-repeat: repeat-y repeat-x;
  background-image: url("static/img/Background.png");
}
</style>