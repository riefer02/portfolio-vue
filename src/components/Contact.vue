<template>
	<v-container>
		<v-row>
			<v-col col="12" md="12" class="d-flex justify-center">
				<v-card class="mx-auto">
					<v-card-text class="d-flex justify-center">
						<h1>Contact Me</h1>
					</v-card-text>
					<v-divider></v-divider>
					<div class="d-flex justify-center">
						<v-card-actions>
							<ContactForm />
						</v-card-actions>
					</div>
				</v-card>
			</v-col>
		</v-row>
	</v-container>
</template>

<script>
import ContactForm from "@/components/ContactForm.vue";
export default {
	name: "Contact",
	components: {
		ContactForm,
	},
	data() {
		return {};
	},
};
</script>

<style></style>
