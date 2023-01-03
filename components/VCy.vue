<template>
    <div class="v-cy">
        <div class="v-cy__num" v-html="num"></div>
        <div class="v-cy__code" v-html="code"></div>
        <div class="v-cy__name" v-html="`${nominal}&nbsp;${name}`"></div>
        <div class="v-cy__value" v-html="`${value.toFixed(2)}&nbsp;₽`"></div>
        <div class="v-cy__change" :class="value > previous ? 'plus' : 'minus'" v-html="value > previous ? '↑' : '↓'"></div>
    </div>
</template>

<script setup>
    const props = defineProps({
        code: String,
        num: String,
        name: String,
        nominal: Number,
        value: Number,
        previous: Number,
    })
</script>
