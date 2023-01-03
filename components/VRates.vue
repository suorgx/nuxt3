<template>
    <div class="v-rates" v-if="rates">
        <v-cy v-for="rate in rates['Valute']"
            :key="rate['CharCode']"
            :code="rate['CharCode']"
            :name="rate['Name']"
            :nominal="rate['Nominal']"
            :value="rate['Value']"
            :previous="rate['Previous']"
            :num="rate['NumCode']"
        ></v-cy>
    </div>
</template>

<script module setup>
    import axios from "axios"
    const { data: rates } = await axios.get('https://www.cbr-xml-daily.ru/daily_json.js')
</script>
