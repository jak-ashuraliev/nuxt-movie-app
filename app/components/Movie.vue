<template>
  <b-col xs="12" md="6" lg="4" >
    <!-- wrap each poster with nuxt-link and route to another page by ID -->
    <nuxt-link :to="'movies/' + id">
      <div>
        <img class="poster-size mb-4 img" :src="poster" :alt="this.alt" />
      </div>
    </nuxt-link>
  </b-col>
</template>

<!-- Receiving props / object to be used in the template above -->
<script>
const baseURL = "http://image.tmdb.org/t/p/w342/";
export default {
  name: "Movie",
  // props and validation
  props: {
    id: {
      type: Number,
      required: true,
      default: undefined
    },  
    poster: {
      type: String,
      default: undefined
    }, 
    alt: {
      type: String,
      required: true,
      default: undefined
    }
  }
};
</script>

<style lang="scss">
// set bootstarp border to 2px.
.card {
  border: 2px solid rgba(0, 0, 0, 0.125);
}
// on click / toggle event, add border to the card
.active {
  border: 2px solid #777;
}
.poster-size {
  width: 100%;
}
.img {
  transform: scale(1);
    -webkit-transform: scale(0.9);
    -ms-transform: scale(0.9);
    transition: transform 350ms ease-in-out;
&:hover {
  transform: translate3d(0, 0, 0);
    -webkit-transform: translate3d(0, 0, 0);
    -ms-transform: translate3d(0, 0, 0);
}
}
</style>
