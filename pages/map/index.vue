<template>
    <div>
        <div v-if="!coordinates" class="search-group">
            <div>
                <v-menu v-model="menu" :close-on-content-click="false">
                    <template v-slot:activator="{ on }">
                        <v-text-field v-model="searchQuery" class="text-field" label="Search for a valid address"
                            @input="validateAndSuggestAddress" v-on="on"></v-text-field>
                    </template>

                </v-menu>
                <div v-if="suggestions.length" v-for="(suggestion, index) in suggestions" class="address-select"
                    @click="selectSuggestion(suggestion)">
                    <span class="search-bar" :key="index">{{ suggestion.place_name }}</span>
                </div>
            </div>
        </div>
        <div class="map-view" v-if="currentCoordinates">
            <Map class="map" :coordinates="currentCoordinates"></Map>
            <div class="side-content">
                <v-btn @click="resetPage" class="btn"> Enter new address.</v-btn>
                <span> {{ "The map indicates air-quality using the Air Quality Index, which is based on a variety of factores.Green is the highest, followed by, light green, yellow, orange, and, finally, Red- the worst quality air." }} </span>
            </div>
        </div>
    </div>
</template>
  
<script>
import Map from '@/components/Map.vue';

export default {
    name: 'DefaultLayout',
    data() {
        return {
            suggestionsList: undefined,
            searchQuery: '',
            menu: true,
            map: null,
            coordinates: undefined
        }
    },
    computed: {
        suggestions() {
            return this.suggestionsList;
        },

        currentCoordinates() {
            return this.coordinates;
        }
    },
    methods: {
        async validateAndSuggestAddress(query) {

            if (this.searchQuery.trim() === '') {
                this.suggestionsList = [];
                return;
            }

            try {
                const response = await this.$axios.get(`https://api.mapbox.com/geocoding/v5/mapbox.places/${query}.json?access_token=pk.eyJ1IjoiamFsZW5wYWlnZSIsImEiOiJjbGxoZ2hyYWYxOXBiM3JxbHZiaWs3cnptIn0.WfyEN9vvHlJpg3euijmy8Q`);
                const data = await response.data;

                // Filter and display only valid addresses from the data
                this.suggestionsList = data.features.filter(feature => feature.place_type.includes('address'));
            } catch (error) {
                console.error(error);
            }
        },

        selectSuggestion(suggestion) {
            this.selectedSuggestion = suggestion;
            this.searchQuery = suggestion.place_name;

            this.coordinates = suggestion.center;
        },

        resetPage() {
            this.suggestionsList = undefined;
            this.searchQuery = '';
            this.menu = true;
            this.map = null;
            this.coordinates = undefined;
        }

    }
}
</script>
  
<style>
.search-group {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    width: 50rem;
    padding-bottom: 2%;
}

.text-field {
    width: 50rem;
}

.search-bar {
    width: 100%;
}

.address-select {
    border: 1px solid gray;
    padding: 4px;
    width: 50rem;
}

.address-select:hover {
    background-color: gray;
}

.map-view {
    display: flex;
    justify-content: space-between;
    width: 100%;
}

.map {
    height: 100%;
    width: 100%;

}

.side-content {
    display: block;
    width: 100%;
    align-items: center;
    justify-content: space-between;
}

.btn {
    padding: 0.2rem;
}
</style>
  