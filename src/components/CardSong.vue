<template>
    <div class="card-song text-center">
      <img :src="Img" :alt="Author" />
      <h6 class="text-uppercase pt-2">{{ Title }}</h6>
      <p class="lv-color m-0">{{ Author }}</p>
      <p class="lv-color m-0">{{ Year }}</p>
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
  width: 180px;
  background-color: #2e3a46;
  padding: 1rem;


.lv-color{
    color: #71716c;
}
img {
    width: 100%;
    aspect-ratio: 1/1;
    object-fit: cover;
  }
  &:hover{
    transform: scale(1.1);
  }
}
</style>