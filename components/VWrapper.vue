<template>
    <div class="v-wrapper">
        <v-input ref="firstNameInput" v-model="value" type="number" name="phone" placeholder="phone" @blur="handleBlur">
            <template v-if="showIcon" #left-icon>
                icon
            </template>
        </v-input>
        <button @click="toggle">Toggle Icon</button>
        <button @click="focus">Focus</button>
        <button @click="clear">Clear</button>
    </div>
    <p>phone: {{ value }}</p>
</template>

<script>
export default {
    name: 'VWrapper',
    data() {
        return {
            value: '',
            showIcon: true,
        };
    },
    methods: {
        clear() {
            this.value = ''
        },
        toggle() {
            this.showIcon = !this.showIcon;
        },
        handleBlur(event) {
            console.log('Blur', event);
        },
        focus() {
            this.$refs['firstNameInput'].focus();
        },
    },
};
</script>

<style scoped>
.v-wrapper {
    display: flex;
    align-items: center;
}
</style>
