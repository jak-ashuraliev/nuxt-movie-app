<template>
  <!-- Container -->
  <b-container class="movie_margin">
    <!-- nuxt-link / route to go back to /movies page -->
    <nuxt-link to="/movies"><b-button variant="secondary" class="mb-4">Back</b-button></nuxt-link>
    <b-row>
      <!-- use data components from returned API -->
      <b-col xs="12" sm="12" md="6" lg="4">
        <b-img class="mb-3" fluid :src="'http://image.tmdb.org/t/p/w342/' + movie_detail.poster_path"></b-img>
      </b-col>
      <b-col xs="12" sm="12" md="6" lg="8">
        <h2 class="display-5"> {{ movie_detail.title }}</h2>
        <p> {{ movie_detail.overview }}</p>
        <p class="text-muted">Release Date: {{ movie_detail.release_date }} </p>
        <p class="text-muted">Language: {{ movie_detail.original_language }} </p>
        <p class="text-muted">Rating: {{ movie_detail.vote_average }} </p>
        <b-img class="hd_icon pb-3" src="../../../assets/hd-icon.png" />
        <br><b-button variant="outline-info">Watch Trailer</b-button><b-button variant="danger" class="ml-2">Add To List</b-button>
      </b-col>
    </b-row>
  </b-container>
  <!-- Container End -->
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      section_title: 'Movie',
      subtitle: "Millions of movies, TV shows and people to discover. Explore now.",
      movie_detail: {}
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
      const res = await axios.get(`https://api.themoviedb.org/3/movie/${this.$route.params.id}?api_key=a07e22bc18f5cb106bfe4cc1f83ad8ed`, config);
      this.movie_detail = res.data;
    } catch (err) {
      console.log(err)
    }
  }
}
</script>

<style>
.movie_margin {
  margin-top: 6rem;
}
.hd_icon {
  width: 2.5rem;
}
</style>