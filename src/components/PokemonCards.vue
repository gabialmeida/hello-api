<!--
This is a reusable component that receives via props an Array of pokemons to be displayed.
In order to keep the design consistent, the prop selectedId exists so it is possible to know
which of the pokemons will keep the focus on them when they are selected.

This component communicates to the HelloAPI via event. When there is a click on one Pokemon
card, it sends the Pokemon Id, so the evolutions can be shown in the parent.

This page uses the component Cards, that is more generic, and can be used to structure cards
in this project or in other projects, which allows code reusability.
-->

<template>
  <div class="cards">
    <card 
      v-for="p in pokemon" 
      :key="p.id" 
      @click="click(p)"
      :class="{ opace: p.id !== selectedId }"
      class="card"
    >
      <template v-slot:title>
        {{ p.name }} #{{ p.id }}
      </template>

      <template v-slot:content>
        <img :src="p.sprite" />
      </template>

      <template v-slot:description>
        <div v-for="type in p.types" :key="type.name">
          {{ type.name }}
        </div>
      </template>
    </card>
  </div>
</template>

<script>
import Card from './Card.vue'

export default {
  components: {
    Card
  },

  props: {
    selectedId: {
      type: Number
    },
    pokemon: {
      // ...
      type: Array
    }
  },

  methods: {
    click(pokemon) {
      this.$emit('pokemonSelected', pokemon)
    }
  }
}
</script>

<style scoped>
img {
  width: 100%;
}

.cards {
  display: flex;
  justify-content: center;
  margin-top: 15px;
}

.opace {
  opacity: 0.5;
}

.card:hover {
  opacity: 1;
}
</style>
