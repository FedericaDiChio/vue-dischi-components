<template>
  <main class="container">
    <section id="album-container">
        <ProductCards v-for="(album, index) in albums" :key="index" :album="album" />
    </section>
  </main>
</template>

<script >
import axios from "axios";
import ProductCards from "./ProductCards.vue";
export default {
  components: { ProductCards },
  name: "Products",
  data() {
    return {
      albums: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.albums = res.data.response;
      });
  },
};
</script>

<style lang="scss">
#album-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;

}
</style>
