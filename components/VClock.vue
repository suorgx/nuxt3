<template>
    <div v-html="time"></div>
    <button @click="isWorking = !isWorking" v-html="isWorking ? 'stop' : 'start'"></button>
</template>

<script>
export default {
    props: {
        color: String
    },
    data() {
        return {
            time: '',
            intervalId: null,
            isWorking: true,
        };
    },

    created() {
        this.updateTime()
        this.intervalId = setInterval(() => {
            this.updateTime()
        }, 1000)
    },

    beforeUnmount() {
        clearInterval(this.intervalId)
    },

    methods: {
        updateTime() {
            if (this.isWorking) {
                this.time = new Date().toLocaleTimeString()
            }
        },
    },
}
</script>

<style lang="scss" scoped>
$mainColor: v-bind(color);

button {
    color: $mainColor;
}
</style>
