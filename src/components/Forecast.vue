<template>
    <div v-if="weatherData">
        <h3>Forecast</h3>
        <b-table striped :items="weatherData.hourly"></b-table>
    </div>
    <div v-else>
        <p>Loading...</p>
    </div>
</template>

<script>
export default {
    name: 'Forecast',
    data() {
        return {
            weatherData: null
        }
    },
    async created() {
        const url = "https://api.openweathermap.org/data/2.5/onecall?lat=47.497913&lon=19.040236&appid=eb978d87450039215931b254857202d7&units=metric";
        const response = await fetch(url);
        const data = await response.json();
        await (this.weatherData = data);
        console.log(data);

        let convertTime = function(unixTime) {
            let dt = new Date(unixTime * 1000)
            let h = dt.getHours()
            let m = "0" + dt.getMinutes()
            let t = h + ":" + m.substr(-2)

            return t
        }    

        this.weatherData.hourly.forEach(hour => {
            hour.dt = convertTime(hour.dt);
            hour.weather = hour.weather[0].main;
        });
    }
}
</script>