<template>
	<v-combobox
		multiple
		v-model="tags"
		:label="label"
		append-icon
		chips
		deletable-chips
		class="tag-input"
		:search-input.sync="search"
		@keyup.tab="updateTags"
		@paste="updateTags"
		@change="emitValue"
	>
	</v-combobox>
</template>
<script>
export default {
	name: "TagsInput",
	props: {
		label: {
			type: String,
			required: true,
		},
	},
	data: () => {
		return {
			tags: [],
			search: "",
		};
	},
	methods: {
		updateTags() {
			this.$nextTick(() => {
				this.select.push(...this.tags.split(","));
				this.$nextTick(() => {
					this.tags = "";
				});
			});
		},
		emitValue: function() {
			this.$emit("input", this.tags);
		},
	},
};
</script>
<style></style>
