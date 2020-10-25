<template>
  <!-- Container -->
  <b-container class="movies">
    <h2 class="pt-5 display-4 text-muted">{{ section_title }}</h2>
    <p class="lead mb-4 text-muted">{{ subtitle }}</p>
    <b-row>
      <!-- Movie component pulled from its own file and using props for all attributes -->
      <Movie
        v-for="movie in movies"
        :key="movie.id"
        :id="movie.id"
        :poster="'http://image.tmdb.org/t/p/w342/' + movie.poster_path"
        :alt="movie.title"
      />
   </b-row>
    
  </b-container>
  <!-- Container End -->
</template>

<!-- All content is from variables in the <script> section of the .vue file. -->
<script>

import axios from "axios"
import Movie from "../../components/Movie";

// API KEY and API URL 
const API_KEY = "a07e22bc18f5cb106bfe4cc1f83ad8ed";
const API_URL = "https://api.themoviedb.org/3/movie/popular?api_key=";

export default {
  components: { Movie },
  data() {
    return {
      section_title: "Popular Movies",
      subtitle:
        "Millions of movies, TV shows and people to discover. Explore now.",
      movies: []
    };
  },
  head() {
      return {
        title: this.section_title,
        meta: [
          // set the HTML Head tags for the current page for SEO
          {
            hid: 'description',
            name: 'description',
            content: 'A list of most popular movies and TV shows.'
          }
        ]
      }
    },
    // implement a lifecycle hook that depends on async operations
    async created() {
      const config = {
        headers: {
          Accept: "application/json"
        }
      };
      // making GET request and using Async/Await with Axios
      // use error handing in axios using try / catch
      try {
        const res = await axios.get(API_URL + API_KEY, config);
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
img {
  width: 100%;
}
</style>
