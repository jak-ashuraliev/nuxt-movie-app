<template>
  <div>
    <Nuxt />
    <AppNav />
    <AppFooter />
  </div>
</template>

<script>
import AppNav from "../components/AppNav";
import AppFooter from "../components/AppFooter";
export default {
  components: {
    AppNav,
    AppFooter
  }
};
</script>

<style></style>
