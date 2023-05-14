<template>
    <div>
        <label :for="fieldName" class="py-1">{{ label }}</label>
        <select
            :id="fieldName"
            :name="fieldName"
            class="h-8 p-1 border border-gray-300 border-solid"
            @input="$emit('update:modelValue', $event.target.value)"
        >
            <option
                class="w-full"
                v-if="selectOptions !== null"
                v-for="(option, index) in selectOptions"
                :key="'select-'+index"
                :value="option.value"
                :selected="selectedOption === option.value"
            >{{ option.label }}</option>
        </select>
        <div v-if="fieldInfo !== null" class="text-gray-500 italic text-base">{{ fieldInfo }}</div>
        <div v-if="error" class="text-red-500 italic text-base">{{ error }}</div>
    </div>
</template>

<script>
export default {
    name: "SelectDropdown",
    props: {
        fieldName: {
            required: true,
            type: String
        },
        label: {
            required: true,
            type: String
        },
        modelValue: [String, Date, Object, Number, Boolean],
        error: [String, Number],
        selectOptions: {
            required: false,
            type: Array,
            default: null
        },
        selectedOption: {
            required: false,
            type: String,
            default: ""
        },
        fieldInfo: {
            required: false,
            type: String,
            default: null
        },
    },
    emits: ['update:modelValue'],
}
</script>
