<template>
	<v-card class="elevation-6 pa-6">
		<v-form v-model="valid" @submit="formSubmit">
			<v-row>
				<v-col cols="12" md="12">
					<TextInput
						label="Title"
						v-bind:counter="10"
						v-bind:required="true"
						v-bind:rules="titleRules"
						v-model="form.title"
					/>
				</v-col>
				<v-col cols="12" md="12">
					<TextAreaInput
						label="Summary"
						v-bind:counter="300"
						v-bind:required="true"
						@created="handleCreate"
						v-bind:rules="summaryRules"
						v-model="form.summary"
					/>
				</v-col>

				<v-col cols="12" md="12">
					<TagsInput label="Tags" v-model="form.tags" />
					<TagsInput label="Knowledges" v-model="form.knowledges" />
					<TagsInput label="Producers" v-model="form.producers" />
					<TextInput label="Link" v-model="form.link" />
					<ImageUploader
						v-model="form.images"
						v-on:updateValue="updateImages"
					/>
				</v-col>
				<v-row class="d-flex justify-center">
					<v-btn x-large dark type="submit">Submit</v-btn>
				</v-row>
			</v-row>
		</v-form>
	</v-card>
</template>
<script>
import ImageUploader from "@/components/InputTerminal/ImageUploader.vue";
import TagsInput from "@/components/InputTerminal/TagsInput.vue";
import TextInput from "@/components/InputTerminal/TextInput.vue";
import TextAreaInput from "@/components/InputTerminal/TextAreaInput.vue";

export default {
	name: "InputTerminal",
	components: {
		TagsInput,
		ImageUploader,
		TextInput,
		TextAreaInput,
	},
	data: () => ({
		valid: false,
		form: {
			title: "",
			summary: "",
			tags: [],
			knowledges: [],
			producers: [],
			link: "",
			images: [],
		},
		titleRules: [
			(v) => !!v || "Title is required",
			(v) => v.length <= 20 || "Name must be less than 20 characters",
		],
		summaryRules: [
			(v) => !!v || "Summary is required",
			(v) =>
				v.length <= 300 || "Summary must be less than 300 characters",
		],
	}),
	methods: {
		updateImages(payload) {
			this.form.images = payload;
		},
		handleCreate() {
			console.log("Child has been created");
		},
		formSubmit(e) {
			e.preventDefault();
			console.log(this.form);
			this.axios
				.post(`/api/v1/projects/create`, {
					title: this.form.title,
					summary: this.form.summary,
					tags: this.form.tags,
					knowledges: this.form.knowledges,
					producers: this.form.producers,
					link: this.form.link,
					images: this.form.images,
				})
				.then(function(response) {
					console.log(response.data);
					console.log("Project successfully saved in database.");
				})
				.catch(function(error) {
					if (error.response) {
						console.log(error.response);
					} else if (error.request) {
						console.log(error.request);
					} else {
						console.log("Error", error.message);
					}
				});
		},
	},
};
</script>
<style>
.v-text-field__slot {
	padding-bottom: 0.8rem;
}
</style>
