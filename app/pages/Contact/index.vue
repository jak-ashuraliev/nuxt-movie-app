<template>
  <!-- Container -->
  <b-container class="contact">
    <h2 class="pt-5 display-4 text-muted">{{ header }}</h2>
    <p class="lead mb-4 text-muted">{{ subtitle }}</p>
    <b-row class="mt-4 justify-content-md-center">
      <b-col></b-col>
      <b-col cols="8" >
        <ContactForm/>
      </b-col>
      <b-col></b-col>
    </b-row>
  </b-container>
  <!-- Container End -->
</template>

<script>
import ContactForm from '../../components/ContactForm'
export default {
  data() {
    return {
      header: "Contact Us",
      subtitle: "If you have any questions about our services, please do not hesitate to contact us."
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
