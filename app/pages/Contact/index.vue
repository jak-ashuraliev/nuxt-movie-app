<template>
  <!-- Container -->
  <b-container class="contact">
    <h2 class="pt-5 display-4 text-muted">{{ title }}</h2>
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
      title: "Contact Us",
      subtitle: "If you have any questions about our services, please do not hesitate to contact us."
    };
  },
  head() {
      return {
        title: this.title,
        meta: [
          // set the HTML Head tags for the current page for SEO
          {
            hid: 'description',
            name: 'description',
            content: 'Contact Nuxt Movie App if you have any questions.'
          }
        ]
      }
    }
};
</script>

<!--Styling with scss -->
<style scoped lang="scss">
.contact {
  margin-top: 3rem;
}
</style>
