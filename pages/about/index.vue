<template>
    <div>
        <h1>About Our Project</h1>
        <div class="about-text">
            <span class="span">As three Washintonians, we are no strangers to poor air quality. Between wild fires, smog
                from Seattle, and other pollutants, we are as aware as any that air quality matters, and being aware of it
                is necessary. Educating people on pollution and seeing its real effects is key in combatting the climate
                crisis.</span>
            <span class="span">In a world plagued by climate change and polution, the need for everyday people to be aware
                of the saftey of their air is essential. Our tool provides an easy-to-use map that displays real-time air
                quality info.</span>
            <span>The air quality data is grabbed from OpenWeatherMap.org's air quality index API, which summarizes the air
                quality into a 1 to 5 scale based on the concentration of pollutants like Carbon Monoxide and Sulfur
                Dioxide.</span>
            <v-card>
                <v-card-title>
                    Air Quality Index Information- Know Your Pollutants!
                </v-card-title>
                <v-card-text>


                    SO2 (Sulfur Dioxide):

                    Source: Primarily comes from burning fossil fuels containing sulfur, like coal and oil.
                    Effects: Can irritate the respiratory system, leading to respiratory problems. It contributes to acid
                    rain, harming aquatic life and vegetation.
                </v-card-text>
                <v-card-text>
                    NO2 (Nitrogen Dioxide):

                    Source: Mainly produced by combustion processes in vehicles and industrial facilities.
                    Effects: It can aggravate respiratory conditions, such as asthma, and contribute to the formation of
                    ground-level ozone and acid rain.
                </v-card-text>
                <v-card-text>

                    PM10 (Particulate Matter 10):

                    Source: Includes various particles from construction, industrial processes, and combustion.
                    Effects: Inhalation can lead to respiratory and cardiovascular problems, particularly among vulnerable
                    populations like children and the elderly.
                </v-card-text>
                <v-card-text>

                    PM2.5 (Particulate Matter 2.5):

                    Source: Fine particles from sources like vehicle exhaust, industrial emissions, and wildfires.
                    Effects: Even more dangerous than PM10, as these particles can penetrate deep into the lungs and even
                    enter the bloodstream, causing a wide range of health problems.
                </v-card-text>
                <v-card-text>

                    O3 (Ozone):

                    Source: Forms in the atmosphere due to chemical reactions between oxides of nitrogen (NOx) and volatile
                    organic compounds (VOCs) in the presence of sunlight.
                    Effects: High levels of ground-level ozone can cause respiratory problems, particularly in hot weather.
                    It can also harm vegetation.
                </v-card-text>
                <v-card-text>

                    CO (Carbon Monoxide):

                    Source: Produced by incomplete combustion of carbon-containing fuels.
                    Effects: Can be deadly in high concentrations, as it interferes with the body's ability to transport
                    oxygen. Even at lower levels, it can cause headaches and fatigue.
                    Air pollution, which often contains a mixture of these pollutants, poses significant health and
                    environmental risks. Efforts to reduce emissions and improve air quality are crucial for protecting
                    public health and the environment.
                </v-card-text>
            </v-card>
        </div>

    </div>
</template>
  
<script>
export default {
    name: 'DefaultLayout',
    data() {
    },
    methods: {
    }
}
</script>
  
<style>
.about-text {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    width: 50rem;
}

.span {
    padding-bottom: 1rem;
}
</style>
  