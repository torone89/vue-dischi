<template>
  <!-- COMPONENTE GENERATE DISCO E LOGICA V-FOR -->

  <main>
    <div class="container">
      <div class="disc-card-box row justify-content-between">
        <generate-disco
          v-for="(disc, index) in albumsList"
          :key="index"
          :disc="disc"
        />
        />
      </div>
    </div>
  </main>
</template>

<script>
import GenerateDisco from "./GenerateDisco.vue";

export default {
  name: "DiscoSection",
  components: {
    GenerateDisco,
  },
  props: { albumsList: Array },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/vars";

main {
  background-color: $bg-color;
}

.container {
  padding: 20px 120px;
}
</style>
