<template>
  <!-- Container -->
  <b-container class="contact">
    <h2 class="pt-5 display-4 text-muted">{{ header }}</h2>
    <p class="lead mb-4 text-muted">{{ subtitle }}</p>
  </b-container>
  <!-- Container End -->
</template>

<script>
export default {
  data() {
    return {
      header: "Contact Us",
      subtitle: "Subtitle goes here."
    };
  }
};
</script>

<!--Styling with scss -->
<style scoped lang="scss">
.contact {
  margin-top: 3rem;
}
</style>
