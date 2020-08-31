<template>
  <v-col cols="12" sm="4">
    <v-card class="mx-auto" max-width="400">
      <v-img
        class="white--text align-end"
        height="200px"
        :src="this.item.image"
      >
        <v-card-title>{{ this.item.title }}</v-card-title>
      </v-img>

      <v-card-subtitle class="pb-0">Tags</v-card-subtitle>

      <v-card-text class="text--primary">
        <div>{{ this.item.description }}</div>
      </v-card-text>

      <v-card-actions>
        <v-btn color="orange" text>
          Share
        </v-btn>

        <v-btn color="orange" text>
          <a href="http://www.valuesproject.io">Explore</a>
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: "Card",
  props: {
    item: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {};
  },
};
</script>

<style>
.v-application a {
  color: inherit;
  text-decoration: none;
}
</style>
