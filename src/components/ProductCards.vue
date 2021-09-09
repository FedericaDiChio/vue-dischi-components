<template>
  <div class="card">
    <img :src="album.poster" :alt="album.title" />
    <h2 class="title">{{ album.title.toUpperCase() }}</h2>
    <address class="author">{{ album.author }}</address>
    <time :datetime="album.year" class="year">{{ album.year }}</time>
  </div>
</template>

<script>
export default {
  name: "ProductCards",
  props: ["album"],
};
</script>

<style lang="scss" scoped>
    .card {
  padding: 20px;
  margin: 20px;
  flex-basis: 200px;
  text-align: center;
  min-height: 350px;
    }
    img {
    width: 100%;
    height: auto;
}

.title {
  font-size: 18px;
  color: #fff;
  margin: 15px 0;
}
.author {
   font-size: 16px;
}
.year {
  font-size: 15px;
}

</style>