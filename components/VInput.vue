<template>
    <div
        class="v-input"
        :class="{
      'v-input__icon': $slots['left-icon'],
      'v-input__icon-left': $slots['left-icon'],
    }"
    >
        <span v-if="$slots['left-icon']" class="v-input__icon">
            <slot name="left-icon" />
        </span>
        <input ref="input" v-model="customModel" v-bind="$attrs" class="v-input__text-field" />
    </div>
</template>

<script>
export default {
    name: 'VInput',
    inheritAttrs: false,
    props: {
        modelValue: String,
    },
    emits: {
        'update:modelValue': null,
    },
    computed: {
        customModel: {
            get() {
                return this.modelValue;
            },
            set(value) {
                this.$emit('update:modelValue', value);
            },
        },
    },
    methods: {
        focus() {
            this.$refs['input'].focus();
        },
    },
};
</script>
