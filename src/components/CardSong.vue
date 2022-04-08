<template>
  <div class="">
    <div class="card-song">
      <img :src="Img" :alt="Author" />
      <h3 class="fs-6">{{ Title }}</h3>
      <p>{{ Author }}</p>
      <p>{{ Year }}</p>
    </div>
  </div>
</template>

<script>

export default {
  name: "CardSong",
  props: {
    Song: Array,
    Img: String,
    Title: String,
    Author: String,
    Year: String,
  },
};
</script>

<style lang="scss" scoped >
.card-song {
  color: white;
  width: 200px;
  background-color: #2e3a46;


img {
    width: 100%;
    aspect-ratio: 1/1;
    object-fit: cover;

  }
}
</style>