<template>
  <div>
    <base-header />
    <disco-section :albumsList="albumsList" />
  </div>
</template>

<script>
import DiscoSection from "./components/DiscoSection.vue";
import BaseHeader from "./components/BaseHeader.vue";
import "./assets/scss/style.scss";
import axios from "axios";
export default {
  name: "App",
  components: {
    BaseHeader,
    DiscoSection,
  },
  data() {
    return {
      albumsList: [],
    };
  },

  methods: {
    GetAlbums() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          console.log(res.data);
          this.albumsList = res.data.response;
        });
    },
  },
  mounted() {
    this.GetAlbums();
  },
};
</script>

