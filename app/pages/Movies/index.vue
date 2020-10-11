<template>
  <!-- Container -->
  <b-container class="movies">
    <h2 class="pt-5 display-4 text-muted">{{ header }}</h2>
    <p class="lead mb-4 text-muted">{{ subtitle }}</p>
    <b-row>
      <!-- ImgCard component pulled from its own file and using props for all attributes -->
      <Movie
        v-for="movie in movies"
        :key="movie.id"
        :id="movie.id"

        :title="movie.title"
        :src="movie.poster_path"
          
      />


<!-- 
       <Movie
        v-for="movie in movies"
        :key="movie.id"
        :imgList="imgList"
        :src="imgList.url"
        :alt="imgList.alt"
        :title="movie."
        :text="imgList.text"
        :btn_text="imgList.btn_text"
        :last_update="imgList.last_update"
      /> -->

    </b-row>
    
  </b-container>
  <!-- Container End -->
</template>

<!-- All content is from variables in the <script> section of the .vue file. -->
<script>

import axios from "axios"
import Movie from "../../components/Movie";

export default {
  components: { Movie },
  data() {
    return {
      // header: "Movies",
      // subtitle:
      //   "Lorem ipsum dolor sit amet consectetur adipisicing elit, Eos repudiandae officiis dolores perspiciatis pariatur culpa.",
      movies: []
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      const res = await axios.get("https://api.themoviedb.org/3/movie/now_playing?api_key=a07e22bc18f5cb106bfe4cc1f83ad8ed", config);
      this.movies = res.data.results;
    } catch (err) {
      console.log(err)
    }
  }
};
</script>

<!--Styling with scss -->
<style scoped lang="scss">
.movies {
  margin-top: 3rem;
}
</style>
