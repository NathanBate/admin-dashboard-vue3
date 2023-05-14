<template>
    <div>
        <label :for="fieldName" class="py-1">{{ label }}</label>
        <input
            class="w-8 h-8"
            :class="{ 'nbfhCheckboxIsChecked': modelValue, 'nbfhCheckboxIsNotChecked': ! modelValue }"
            :id="fieldName"
            :name="fieldName"
            type="checkbox"
            :checked="modelValue"
            :value="modelValue"
            @input="$emit('update:modelValue', $event.target.checked)"
        />
        <div v-if="fieldInfo !== null" class="text-gray-500 italic text-base">{{ fieldInfo }}</div>
        <div v-if="error" class="text-red-500 italic text-base">{{ error }}</div>
    </div>
</template>

<script>
export default {
    name: "LightSwitch",
    props: {
        fieldName: {
            required: true,
            type: String
        },
        label: {
            required: true,
            type: String
        },
        modelValue: [Boolean],
        error: [String, Number],
        fieldInfo: {
            required: false,
            type: String,
            default: null
        },
    },
    emits: ['update:modelValue'],
}

</script>
<style>

</style>
