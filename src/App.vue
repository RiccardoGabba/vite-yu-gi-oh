<template>
  <main>
    <div>
      <h1>Carte Yu gi oh</h1>
    </div>
     
      <selectorType @giuseppe= "selectElement"  />
    
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
        params: null,
      }
    },
    methods: {
      getCards(){
        const url = store.apiUrl
        axios.get(url, {params: this.params}).then(response => {
          console.log(response.data.data)
          this.store.cardList = response.data.data
        })
      },
      selectElement (search){
        this.params = {archetype: search}
        this.getCards()
      }
    },
    created() {
      this.getCards()
    }
  }
</script>

<style lang="scss" scoped>
</style>
