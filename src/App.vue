<template>
  <div>
    <base-header />
    <SelectBar :genres="genres" @genre-changed="albumsFilter" />
    <disco-section :albumsList="filteredListGenre" />
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
    albumsFilter(value) {
      let filteredListGenre;
      if (value === "All") {
        filteredListGenre = this.albumsList;
      } else {
        filteredListGenre = this.albumsList.filter((album) => {
          return album.genre === value;
        });
      }
      this.filteredListGenre = filteredListGenre;
    },
    GetAlbums() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          console.log(res.data);
          this.albumsList = res.data.response;
          this.filteredListGenre = res.data.response;
        });
    },
  },
  computed: {
    genres() {
      let genres = [];
      for (let album of this.albumsList) {
        if (!genres.includes(album.genre)) {
          genres.push(album.genre);
        }
      }
      return genres;
    },
  },

  mounted() {
    this.GetAlbums();
  },
};
</script>

