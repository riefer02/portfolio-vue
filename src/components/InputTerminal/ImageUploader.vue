<template>
	<div>
		<label class="v-label theme--light">Image</label>
		<handyUploader
			:documentAttachment.sync="handyAttachments"
			:fileUploaderType="'simple'"
			:maxFileSize="10240"
			:imageCompressor="true"
			:imageCompressLevel="0.8"
			:maxFileCount="10"
			:badgeCounter="true"
			:thumb="false"
			:changeFileName="true"
			:addFileDescription="true"
			:addFileTag="true"
			:tags="['Tag 1', 'Tag 2', 'Tag 3', 'Tag 4']"
		/>
	</div>
</template>

<script>
import handyUploader from "handy-uploader/src/components/handyUploader";

export default {
	name: "ImageUploader",
	components: {
		handyUploader,
	},
	data: () => ({
		handyAttachments: [],
	}),
	watch: {
		handyAttachments: function() {
			console.log(this.handyAttachments);
			this.$emit("updateValue", this.handyAttachments);
		},
	},
	methods: {
		emitValue: function() {
			this.$emit("input", this.handyAttachments);
		},
	},
};
</script>

<style></style>
