<template>
	<v-text-field
		:label="label"
		v-model="input"
		:rules="rules"
		:counter="counter"
		@change="emitValue"
	/>
</template>

<script>
export default {
	name: "TextInput",
	props: {
		label: {
			type: String,
			required: true,
		},
		counter: {
			type: Number,
		},
		rules: {
			type: Array,
		},
		required: {
			type: Boolean,
		},
	},
	created() {
		this.$emit("created");
	},
	data: () => ({
		input: "",
	}),
	methods: {
		emitValue: function() {
			this.$emit("input", this.input);
		},
	},
};
</script>

<style></style>
