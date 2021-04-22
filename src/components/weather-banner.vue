<template>
    <header class="weather-banner">
        <span v-if="currentTemp">
            <strong>{{ currentTemp }}&deg;</strong> Is the
        </span>
        <span>Current Outside Temperature</span>
    </header>
</template>

<script>
import axios from 'axios';

export default {
    name: 'WeatherBanner',
    data() {
        return {
            currentTemp: null,
        };
    },
    created() {
        this.getTemp();
    },
    methods: {
            // define function as async to be able to await later in function.
        async getTemp() {
            // set variables (there are no errors in these strings)
            const url = 'http://api.openweathermap.org/data/2.5/weather';
            const zipCode = '85226';
            const apiKey = 'eab29b6df2f075a12235544ff5dcdd52';
            const units = 'imperial';
            const endpoint = `${url}?zip=${zipCode}&appid=${apiKey}&units=${units}`;

            // make api call
            // need to make this an await in order to get the response before moving on to setting value.
            const response = await axios.get(endpoint);

            // display current temp on page
            // now we have waited for the promise to finish and can display the information correctly
            this.currentTemp = response.data.main.temp;

        },
    },
};
</script>

<style lang="scss" scoped>
.weather-banner {
    padding: 1rem;
    text-align: right;
}
</style>
