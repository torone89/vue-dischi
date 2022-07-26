<template>
  <div class="hello">
    <header>
      <div class="container h-100 d-flex align-items-center">
        <img src="../assets/img/spotify-logo.svg" alt="Logo" />
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: "BaseHeader",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/vars";
header {
  background-color: $primary-color;
  height: 100px;
}
img {
  height: 50%;
}
</style>
