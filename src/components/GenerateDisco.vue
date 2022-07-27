<template>
  <div class="disc-card text-center m-3 col-2 p-2">
    <img class="image-album mt-2" :src="disc.poster" />
    <div class="title pt-2 mt-2">{{ disc.title }}</div>
    <div class="info">{{ disc.author }}</div>
    <div class="info">{{ disc.year }}</div>
  </div>
</template>

<script>
export default {
  name: "GenerateDisco",
  props: {
    disc: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/vars";
.disc-card {
  background-color: $primary-color;
}

.image-album {
  width: 90%;
}
.title {
  font-size: 0.9rem;
  text-transform: uppercase;
  font-weight: 600;
  color: $title-card;
}
.info {
  font-size: 0.8rem;
  color: $info-card;
}
</style>