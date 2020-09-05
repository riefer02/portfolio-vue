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
  mounted() {
    this.fetchData();
  },
  watch: {
    // call again the method if the route changes
    $route: "fetchData",
  },
  methods: {
    fetchData() {
      console.log("fetching");
      this.error = this.projects = null;
      this.loading = true;
      this.projects = [];
      const self = this;
      this.axios
        .get("/api/v1/projects/")
        .then((res) => {
          this.loading = false;
          self.projects = res.data.projects;
          // this.$set(this.projects, this.projects.name, res.data.totalValues);
          console.log("Projects Updated");
        })
        .catch((error) => {
          this.error = error.toString();
        });
    },
  },
  data: () => ({
    projects: [],
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
