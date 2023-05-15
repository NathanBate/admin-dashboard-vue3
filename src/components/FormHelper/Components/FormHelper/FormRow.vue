<template>
	<div>

		<div v-if="columns===1" class="flex flex-col py-2 sm:py-4">
			<slot name="cell" class="w-full py-2 sm:py-0"></slot>
		</div>

		<div v-if="columns===2" class="flex flex-col sm:flex-row gap-2 sm:gap-6 py-2 sm:py-4">

			<slot name="leftcell" class="w-full sm:w-1/2 sm:py-0"/>

            <slot name="spacer">
                <div class="sm:w-1/8"/>
                <div class="sm:w-1/8"/>
            </slot>

			<slot name="rightcell" class="w-full sm:w-1/2 sm:py-0"/>

		</div>

	</div>
</template>

<script>
export default {
	props: {
		columns: {
			type: [Number],
			default: 1,
			validator(value) {
				if ((value < 1) || (value > 2)) {
					console.warn("Row: There can only be 1 or 2 columns.")
					return false;
				} else {
					return true;
				}
			}
		}
	}
}
</script>
