<template>
  <main>
    <div class="container">
      <div class="row">
        <!--Aggiungere le cards qui-->
        <Cards />
      </div>
    </div>
  </main>
</template>

<script>
import Cards from './components/Cards.vue'
  export default {
    name: 'App',
    components: {
      Cards,
    },
    data() {
      return {

      }
    },
    methods: {

    },
  }
</script>

<style lang="scss" scoped>

</style>