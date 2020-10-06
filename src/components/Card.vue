<template>
  <v-col cols="12" sm="4">
    <v-card class="mx-auto" max-width="400">
      <v-img
        class="white--text align-end"
        :src="this.item.image"
        height="200px"
      >
        <v-card-title>{{ this.item.title }}</v-card-title>
      </v-img>

      <v-card-subtitle class="pb-0" v-for="tag in this.item.tags" :key="tag"
        >#{{ tag }}</v-card-subtitle
      >

      <v-card-text class="text--primary">
        <div>{{ this.item.summary }}</div>
      </v-card-text>

      <v-card-actions>
        <v-btn color="orange" text>
          Share
        </v-btn>
        <a href="http://www.valuesproject.io">
          <v-btn color="orange" text>
            Explore
          </v-btn>
        </a>
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
