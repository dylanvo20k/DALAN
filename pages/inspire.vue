<template>
  <div>
    <v-row>
      <v-col class="text-center">
        Meet the team
        <v-card class="custom-card">
          <v-card-title class="name">
            Jalen Paige
          </v-card-title>
          <v-card-text class="description">
            Lightskin king from Mukilteo, WA.
            Santa Clara University co'26
          </v-card-text>
          <img src="jalen.jpg" alt="Image" class="card-image" />
        </v-card>
      </v-col>
    </v-row>
    <!-- Second Card -->
    <v-card class="custom-card2">
      <v-card-title class="name2">
        Dylan
      </v-card-title>
      <v-card-text class="description2">
        Northeastern warrior
      </v-card-text>
      <img src="dylan.jpg" alt="Image2" class="card-image2" />
    </v-card>
  </div>
</template>

<script>
export default {
  name: 'Team'
}
</script>

</template>
<script>

export default {
  name: 'Team'
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');

.text-center {
  top: 1%;
  left: 8%;
  text-align: center;
  color: white;
  font-size: 10rem;
  font-family: 'Bebas Neue', sans-serif;

}

.custom-card {
  width: 80%;
  height: 500px;
  margin: 0 auto;
  /* Centers the card horizontally */
  margin-bottom: 20px;
}

.custom-card2 {
  width: 80%;
  height: 500px;
  margin: 0 auto;
}

.name {
  width: 50%;
  color: white;
  font-size: 2.5rem;
  font-family: 'Bebas Neue', sans-serif;
}

.name2 {
  width: 50%;
  color: white;
  font-size: 2.5rem;
  font-family: 'Bebas Neue', sans-serif;
}

.description {
  width: 50%;
  color: white;
  font-size: 1.5rem;
  font-family: 'Bebas Neue', sans-serif;
}

.description2 {
  width: 50%;
  color: white;
  font-size: 1.5rem;
  font-family: 'Bebas Neue', sans-serif;
}

.card-image {
  position: absolute;
  top: 50%;
  right: 0;
  transform: translate(0, -50%);
  height: 100%;
  width: 50%;
  object-fit: cover;
}

.card-image2 {
  position: absolute;
  top: 50%;
  right: 0;
  transform: translate(0, -50%);
  height: 100%;
  width: 50%;
  object-fit: cover;
}</style>



