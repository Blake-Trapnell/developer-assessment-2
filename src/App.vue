<template>
    <div id="app">
        <WeatherBanner />
        <ChapmanCares />
        <FormFill />
    </div>
</template>

<script>
import WeatherBanner from '@/components/weather-banner';
import ChapmanCares from '@/components/chapman-cares';
import FormFill from '@/components/form-fill';

export default {
    name: 'App',
    components: {
        WeatherBanner,
        ChapmanCares,
        FormFill,
    },
};
</script>

<style lang="scss">
:root {
    --max-width: 960px;
    --color-highlight: #f5c700;
}
* {
    box-sizing: border-box;
}
body {
    margin: 0;
    padding: 2rem;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    max-width: var(--max-width);
    margin: 0 auto;
}
</style>
