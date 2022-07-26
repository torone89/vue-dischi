<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <!-- COMPONENTE GENERATE DISCO E LOGICA V-FOR -->
    <generate-disco />
  </div>
</template>

<script>
import GenerateDisco from "./GenerateDisco.vue";
export default {
  name: "DiscoSection",
  components: {
    GenerateDisco,
  },
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
