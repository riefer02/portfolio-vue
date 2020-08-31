<template>
	<div class="home">
		<!-- <h1>riefer.io</h1> -->
		<Carousel />
		<CardDeck />
		<v-divider></v-divider>
		<Contact />
	</div>
</template>

<script>
// @ is an alias to /src
import Carousel from "@/components/Carousel.vue";
import CardDeck from "@/components/CardDeck.vue";
import Contact from "@/components/Contact.vue";

export default {
	name: "Home",
	components: {
		Carousel,
		CardDeck,
		Contact,
	},
};
</script>
