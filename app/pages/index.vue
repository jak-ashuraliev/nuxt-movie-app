<template>
  <!-- Jumbotron -->
  <b-jumbotron
    class="rounded-0 text-light text-center d-flex justify-content-center align-items-center"
  >
    <!-- bg image overlay div  -->
    <div class="img-overlay"></div>
    <b-container class="p-0">
      <h1 class="display-3">{{ title }}</h1>
      <p class="lead">{{ subtitle }}</p>
      <nuxt-link to="/movies"><b-button variant="primary" size="lg" class="m-1"
        >Now Playing</b-button></nuxt-link>
    </b-container>
  </b-jumbotron>
  <!-- Jumbotron End  -->
</template>

<!-- All content is from variables in the <script> section of the .vue file. -->
<script>
export default {
  data: () => {
    return {
      title: "MOVIE APP",
      subtitle:
        "Millions of movies, TV shows and people to discover. Explore now.",
      message:
        "Our website is currently undergoing scheduled maintenance. Thank you for your patience!",
      dismissSecs: 6,
      dismissCountDown: 0,
      showBtn: true
    };
  },
  methods: {
    countDownChanged(dismissCountDown) {
      this.dismissCountDown = dismissCountDown;
    },
    showAlert() {
      this.dismissCountDown = this.dismissSecs;
    }
  }
};
</script>

<!--Styling with scss -->
<style scoped lang="scss">
$yellow: #ffb617;

.lead {
  max-width: 50%;
  margin: 0 auto 1rem;
}
.alert-danger {
  width: 75%;
  margin: auto;
  .progress {
    height: 0.25rem;
    margin-top: 0.5rem;
  }
}

// Jumbotron & Background Img
.jumbotron {
  // margin-top: 3.5rem;
  margin-bottom: 0 !important;
  min-height: 100vh;
  background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url("https://images.unsplash.com/photo-1503726876301-67e54d319b60?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1443&q=80");
  background-size: cover;
  background-position: left;
  background-repeat: no-repeat;

  // Main heading
  h1 {
    font-weight: 700;
  }
}

// Tooltip bg color override
.tooltip-inner {
  background-color: $yellow !important;
}

.tooltip.bs-tooltip-right .arrow:before {
  border-right-color: $yellow !important;
}
</style>
