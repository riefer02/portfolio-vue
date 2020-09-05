<template>
	<div class="home">
		<Carousel />
		<CardDeck />
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
