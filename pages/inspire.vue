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

            Hello! I'm a rising sophomore from Santa Clara University who loves music and long walks on the beach. I also
            love cats.
          </v-card-text>
          <img src="jalen.jpg" alt="Image" class="card-image" />
        </v-card>
      </v-col>
    </v-row>
    <!-- Second Card -->
    <v-card class="custom-card">
      <v-card-title class="name">
        Dylan Vo
      </v-card-title>
      <v-card-text class="description">
        Yo! I'm a rising freshmen from Northeastern University. I love physics and hope to combine this with software by
        working in the aerospace industry. I also love cats.
      </v-card-text>
      <img src="dylan.jpg" alt="Image2" class="card-image2" />
    </v-card>
    <!-- Third card-->
    <v-card class="custom-card">
      <v-card-title class="name">
        Dylan Neighart
      </v-card-title>
      <v-card-text class="description">
       Chao! I am a computer science major hoping to become a software engineer. My favorite hobbies are coding, cooking, and reading. Also, I love cats.
      </v-card-text>
      <img src="neighart.jpg" alt="Image3" class="card-image3" />
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
  position: absolute;
  /* Position the text absolutely */
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
}

.card-image3 {
  position: absolute;
  top: 50%;
  right: 0;
  transform: translate(0, -50%);
  height: 100%;
  width: 50%;
  object-fit: cover;
}</style>



