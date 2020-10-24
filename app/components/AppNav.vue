<template>
  <!-- AppNav -->
  <b-navbar toggleable="lg" type="dark" variant="primary" fixed="top">
    <b-img class="logo" src="../assets/logo.png" alt="logo"/>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav class="ml-auto">
        <!-- added routing for all pages using nuxt-link  -->
        <nuxt-link to="/">Home</nuxt-link>
        <nuxt-link to="/movies">Movies</nuxt-link>
        <nuxt-link to="/contact">Contact</nuxt-link>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
  <!-- AppNav End -->
</template>

<script>

export default {
  name: "AppNav"
};
</script>

<style scoped lang="scss">
.logo {
  width: 3rem;
}
a {
  color: white;
  padding-left: 1.5rem;
  text-decoration: none;

  &:hover {
    color: #eee;
  }
}
</style>
