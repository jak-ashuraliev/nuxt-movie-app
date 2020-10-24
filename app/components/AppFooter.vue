<template>
  <!-- Footer -->
  <footer class="text-center p-3 flex-0">
    <small>&copy;{{ footer_text }}</small>
  </footer>
  <!-- Footer End -->
</template>

<!-- All content is from variables in the <script> section of the .vue file. -->
<script>
export default {
  name: "Footer",
  data() {
    return {
      footer_text: ' 2020 Made with Love in Seattle, WA by Jak Ashuraliev.'
    }
  },
};
</script>
