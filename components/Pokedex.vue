<template>
  <div class="container">
    <div class="Logo">
      <img src="img/Logo.png" alt="" />
    </div>
    <div class="row">
      <div
        v-for="pokemon in pokemons"
        :key="pokemon.id"
        class="col-lg-3 card-padding"
      >
        <Card :pokemon="pokemon" />
      </div>
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

<style scoped>
.Logo {
  text-align: center;
}
.Logo > img {
  width: 320px;
  margin-top: 20px;
  margin-bottom: 20px;
}
.card-padding {
  padding-left: 0;
  padding-right: 0;
}
</style>