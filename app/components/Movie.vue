<template>
  <b-col xs="12" md="6" lg="4">
    <b-card-group>
      <b-card
        deck
        :title="this.title"
        img-top
        tag="article"
        class="mb-4"
      >
        <b-card-text>{{ this.title }}</b-card-text>
        <!-- <b-button href="#" variant="primary">{{ imgList.btn_text }}</b-button> -->
        <template>
          <small class="text-muted">{{ this.title }}</small>
        </template>
      </b-card>
      
    </b-card-group>
  </b-col>
</template>

<!-- Receiving props / object to be used in the template above -->
<script>
export default {
  name: "Movie",
  // props and validation
  props: ["title", "poster"]
  
  // {
  //   imgList: {
  //     type: Object,
  //     requred: true
  //   },
  //   title: {
  //     type: String,
  //     required: true,
  //     default: "Default Title"
  //   },
  //   text: {
  //     type: String,
  //     required: true,
  //     default: "Some default text"
  //   },
  //   btn_text: {
  //     type: String,
  //     default: "Disabled"
  //   },
  //   ulr: {
  //     type: String
  //   },
  //   alt: {
  //     type: String,
  //     required: true,
  //     default: "Description of the image"
  //   },
  //   last_update: {
  //     type: String,
  //     required: true,
  //     default: "Last updated time unknown."
  //   }
  // }
};
</script>

<style lang="scss">
.movie {
  padding: 1rem;
  border: 1px solid #eee;
  margin: 1rem 0;
}
// set bootstarp border to 2px.
.card {
  border: 2px solid rgba(0, 0, 0, 0.125);
}
// on click / toggle event, add border to the card
.active {
  border: 2px solid #777;
}
</style>
