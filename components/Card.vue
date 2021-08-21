<template>
  <div>
    <div class="card" :class="pokemon.type[0]">
      <span>#{{ maskZeros(pokemon.id, 3) }}</span>
      <img class="pokeball-img" src="img/pokeball-icon-png-5.png" alt="" />
      <div>
        <h4 class="name-pokemon">{{ pokemon.name.english }}</h4>
        <div v-for="(type, index) in pokemon.type" :key="type + index">
          <div class="type">
            <span class="type-card">{{ type }}</span>
          </div>
        </div>
      </div>
      <img
        class="pokemon_image"
        :src="`https://raw.githubusercontent.com/fanzeyi/pokemon.json/master/images/${maskZeros(
          pokemon.id,
          3
        )}.png`"
        alt=""
      />
    </div>
  </div>
</template>

<script>
export default {
  props: ["pokemon"],
  data() {
    return {
      pokemons_id: [],
    };
  },
  methods: {
    maskZeros(value, padding) {
      let zero = new Array(padding + 1).join("0");
      return (zero + value).slice(-padding);
    },
  },
};
</script>

<style scoped>
.card {
  position: relative;
  padding: 20px;
  height: 170px;
  margin: 10px;
  transition: 0.5s;
}
.card:hover {
  transform: scale(1.1);
}
.card > span {
  position: absolute;
  right: 0;
  top: 5px;
  color: rgba(255, 255, 255, 0.384);
  font-size: 40px;
}
.card > .pokeball-img {
  position: absolute;
  overflow: hidden;
  z-index: 0;
  width: 90px;
  right: 0;
  top: 70px;
}
.name-pokemon {
  color: white;
  font-weight: bold;
}
.pokemon_image {
  position: absolute;
  z-index: 1;
  right: 10px;
  top: 45px;
  width: 120px;
}
.type {
  margin-top: 15px;
}
.type-card {
  border: 0px solid;
  padding: 3px;
  border-radius: 5px;
  font-weight: bold;
  color: white;
  background-color: rgba(17, 17, 17, 0.322);
}
.Grass {
  background-color: #9bcc50;
}
.Bug {
  background-color: #729f3f;
}
.Dragon {
  background-color: coral;
}
.Normal {
  background-color: #a4acaf;
}
.Flying {
  background-color: #3dc7ef;
}
.Ground {
  background-color: #ab9842;
}
.Dark {
  background-color: #707070;
}
.Rock {
  background-color: #a38c21;
}
.Ghost {
  background-color: #7b62a3;
}
.Ice {
  background-color: #52c5e8;
}
.Steel {
  background-color: #9fb8b9;
}
.Fighting {
  background-color: #d56723;
}
.Psychic {
  background-color: #f366b9;
}
.Electric {
  background-color: #efd636;
}
.Fire {
  background-color: #fd7d24;
}
.Fairy {
  background-color: #febaea;
}
.Water {
  background-color: #4592c4;
}
.Poison {
  background-color: #b97fc9;
}
</style>