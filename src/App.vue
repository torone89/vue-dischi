<template>
  <div>
    <base-header />
    <select-bar
      :values="['All', 'Pop', 'Rock', 'Jazz', 'Metal']"
      @selectedGenre="filterGenere"
      :discs="filteredListGenre"
    />
    <disco-section :albumsList="albumsList" />
  </div>
</template>

<script>
import DiscoSection from "./components/DiscoSection.vue";
import BaseHeader from "./components/BaseHeader.vue";
import SelectBar from "./components/SelectBar.vue";
import "./assets/scss/style.scss";
import axios from "axios";
export default {
  name: "App",
  components: {
    BaseHeader,
    DiscoSection,
    SelectBar,
  },
  data() {
    return {
      albumsList: [],
      filteredListGenre: [],
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
    filterGenere(keyword) {
      this.albumsList.filter((disc) => {
        return (
          disc.genre.toLowerCase() === keyword.toLowerCase() ||
          keyword.toLowerCase() === "all"
        );
      });
    },
  },
  mounted() {
    this.GetAlbums();
  },
};
</script>

