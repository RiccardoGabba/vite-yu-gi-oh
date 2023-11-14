<template>
  <main>
    <div>
      <h1>Carte Yu gi oh</h1>
    </div>
    <div>
      <selectorType/>
    </div>
    <div class="container">
      <div class="row">
        <!--Aggiungere le cards qui-->
        <Cards
          v-for="(el) in store.cardList"
          :name="el.name"
          :archetype="el.archetype"
          :image="el.card_images[0].image_url"
        />
      </div>
    </div>
  </main>
</template>

<script>
import Cards from './components/Cards.vue'
import { store } from './data/store'
import axios from 'axios'
import selectorType from './components/SelectorType.vue'
  export default {
    name: 'App',
    components: {
      Cards,
      selectorType
    },
    data() {
      return {
        store,
      }
    },
    methods: {
      getCards(){
        const url = store.apiUrl
        axios.get(url).then(response => {
          console.log(response.data.data)
          this.store.cardList = response.data.data
        })
      }
    },
    created() {
      this.getCards()
    }
  }
</script>

<style lang="scss" scoped>
</style>
