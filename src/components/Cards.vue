<template>
    
  <div class="col-2 text-center">
    <img :src="image">
  
  <h5> {{ name }} </h5>
  <h5> {{ archetype }} </h5>
    </div>  
</template>

<script>
export default {
    name: 'Cards',
    props: {
        image: String,
        name: String,
        archetype: String, 
    },
    data() {
        return {

        }
    }
};
</script>

<style lang="scss" scoped>
img{
    width: 100%;
}
</style>
