<template>
    <div>
        <label :for="fieldName" class="py-1">{{ label }}</label>
        <input
            :id="fieldName"
            :name="fieldName"
            type="number"
            class="h-8 p-2 border border-gray-300 border-solid"
            :min="numberMin !== null ? numberMin : ''"
            :max="numberMax !== null ? numberMax : ''"
            :value="modelValue"
            @input="$emit('update:modelValue', $event.target.value)"
        />
        <div v-if="fieldInfo !== null" class="text-gray-500 italic text-base">{{ fieldInfo }}</div>
        <div v-if="error" class="text-red-500 italic text-base">{{ error }}</div>
    </div>
</template>

<script>
export default {
    name: "NumberField",
    props: {
        fieldName: {
            required: true,
            type: String
        },
        label: {
            required: true,
            type: String
        },
        modelValue: [Number, String],
        error: [String, Number],
        fieldInfo: {
            required: false,
            type: String,
            default: null
        },
        numberMin: {
            type: Number,
            default: null
        },
        numberMax: {
            type: Number,
            default: null
        },
    },
    emits: ['update:modelValue'],
}
</script>
