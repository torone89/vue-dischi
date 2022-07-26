<template>
  <div>
    <base-header />
    <disco-section />
  </div>
</template>

<script>
import DiscoSection from "./components/DiscoSection.vue";
import BaseHeader from "./components/BaseHeader.vue";

export default {
  name: "App",
  components: {
    BaseHeader,
    DiscoSection,
  },
};
</script>

<style lang="scss">
@import "../com/scss/var.sccss";
</style>
