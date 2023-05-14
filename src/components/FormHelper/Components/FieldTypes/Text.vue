<template>
    <div class="flex flex-col">
        <label :for="fieldName" class="py-1">{{ label }}</label>
        <input
            v-if="! textbox"
            :id="fieldName"
            :name="fieldName"
            type="text"
            class="h-8 p-2 border border-gray-300 border-solid"
            maxlength="50"
            :value="modelValue"
            @input="$emit('update:modelValue', $event.target.value)"
        />
        <textarea
            v-else
            :id="fieldName"
            :name="fieldName"
            class="h-24 p-2 border border-gray-300 border-solid"
            :value="modelValue"
            @input="$emit('update:modelValue', $event.target.value)"
        >
        </textarea>
        <div v-if="fieldInfo !== null" class="text-gray-500 italic text-base">{{ fieldInfo }}</div>
        <div v-if="error" class="text-red-500 italic text-base">{{ error }}</div>
    </div>
</template>

<script>

export default {
    name: 'TextInput',
    components: {},
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
        fieldInfo: {
            required: false,
            type: String,
            default: null
        },
        textbox: {
            default: false,
            type: Boolean,
            required: false,
        },
    },
    emits: ['update:modelValue'],
}
</script>
