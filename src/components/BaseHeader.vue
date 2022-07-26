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
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/vars";
header {
  background-color: $bg-color;
  height: 100px;
}
img {
  height: 80%;
  vertical-align: middle;
  line-height: 100px;
}
</style>
