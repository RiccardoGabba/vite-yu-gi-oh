<template>
  <div class="col-2 text-cente bg-black">
    <img :src="image" />
    <div class="text-white  ">
      <h5>{{ name }}</h5>
      <h5>{{ archetype }}</h5>
    </div>
  </div>
</template>

<script>
export default {
  name: "Cards",
  props: {
    image: String,
    name: String,
    archetype: String,
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
img {
  width: 100%;
}
</style>
