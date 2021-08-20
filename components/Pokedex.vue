<template>
  <div>
    <div v-for="pokemon in pokemons" :key="pokemon.id">
      <img :src="maskZeros(pokemon.id, 3)" alt="" />
      {{ pokemon.name.english }}
    </div>
  </div>
</template>

<script>
export default {
  props: ["pokemons"],
  data() {
    return {
      pokemons_id: [],
    };
  },
  methods: {
    maskZeros(value, padding) {
      let zero = new Array(padding + 1).join("0");
      return (
        "https://raw.githubusercontent.com/fanzeyi/pokemon.json/master/images/" +
        (zero + value).slice(-padding) +
        ".png"
      );
    },
  },
};
</script>
