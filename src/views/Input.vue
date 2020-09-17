<template>
	<div class="input">
		<v-container>
			<v-row class="d-flex justify-center">
				<InputTerminal />
			</v-row>
		</v-container>
	</div>
</template>

<script>
// @ is an alias to /src
import InputTerminal from "@/components/InputTerminal/InputTerminal.vue";

export default {
	name: "Input",
	components: {
		InputTerminal,
	},
};
</script>
