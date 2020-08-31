<template>
  <v-container>
    <v-row>
      <Card v-for="item in items" :key="item.title" :item="item" />
    </v-row>
  </v-container>
</template>

<script>
import Card from "@/components/Card.vue";
export default {
  name: "CardDeck",
  components: {
    Card,
  },
  data: () => ({
    items: [
      {
        image:
          "https://images.unsplash.com/photo-1461749280684-dccba630e2f6?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80",
        title: "Developer",
        description: "I am a developer.",
        link: "https://github.com/riefer02",
      },
    ],
  }),
};
</script>
