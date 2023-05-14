<template>
	<form @submit.prevent="store">
		<slot/>
		<div class="mt-4 py-4">
			<loading-button
					v-if="buttonLabel && !submitDisabled"
					:loading="formData.processing"
					class="text-white px-6 py-2"
					type="submit"
          style="background-color: #E12D39;">
				{{ buttonLabel }}
			</loading-button>
            <div v-if="submitDisabled" class="text-red-600">
                {{ disabledSubmitMessage }}
            </div>
			<slot name="buttonRow"></slot>
		</div>
	</form>
</template>

<script>
import LoadingButton from '@/Components/InertiaComponents/LoadingButton'

export default {
	components: {
		LoadingButton,
	},
	props: {
		storePath: String,
		buttonLabel: String,
		formData: {
			required: true,
			type: [Object],
		},
        disabledSubmitMessage: {
            required: false,
            default: null,
            type: [String, null]
        }
	},
    computed: {
      submitDisabled() {
          if (this.disabledSubmitMessage !== null) {
              return true;
          }
          return false;
      },
    },
	methods: {
		store() {
			this.formData.post(this.storePath)
		},
	},
}

</script>
