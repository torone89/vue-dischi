<template>
  <!-- COMPONENTE GENERATE DISCO E LOGICA V-FOR -->

  <main>
    <div class="container">
      <div class="disc-card-box row justify-content-between">
        <generate-disco
          v-for="(album, index) in albumsList"
          :key="index"
          :image="album.poster"
          :title="album.title"
          :author="album.author"
          :year="album.year"
        />
      </div>
    </div>
  </main>
</template>

<script>
import GenerateDisco from "./GenerateDisco.vue";
import axios from "axios";
export default {
  name: "DiscoSection",
  components: {
    GenerateDisco,
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/vars";

main {
  background-color: $bg-color;
}

.container {
  padding: 20px 150px;
}
</style>
