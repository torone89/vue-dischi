<template>
  <div>
    <base-header />
    <disco-section />
  </div>
</template>

<script>
import DiscoSection from "./components/DiscoSection.vue";
import BaseHeader from "./components/BaseHeader.vue";
import "./assets/scss/style.scss";

export default {
  name: "App",
  components: {
    BaseHeader,
    DiscoSection,
  },
};
</script>

