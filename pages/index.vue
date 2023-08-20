<template>
  <div>
    <img src="prehack.png" alt="Background Image" />
    <div class = "vape">
      <h1>dalan</h1>
      <span class="overlay" >based out of mukilteo, wa</span>
    </div>
  </div>
</template>


<script>
export default {
  name: "IndexPage",
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');
  .overlay {
    position: absolute;
    top: 80%;
    left: 8%;
    text-align: center;
    color: white;
    font-size: 1rem;
    font-family: 'Bebas Neue', sans-serif;

}
.vape{
  position: absolute;
  top: 50%;
    left: 50%;
    text-align: center;
    color: white;
    font-size: 2.5rem;
    font-family: 'Bebas Neue', sans-serif;
}

.image-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50px; /* Adjust this based on your design */
  overflow: hidden;
  background-color: rgb(0, 0, 0); /* Optional background color */
}


img {
  max-width: 100%; /* Make sure the image doesn't exceed its container's width */
  max-height: 100%; /* Make sure the image doesn't exceed its container's height */
} 

</style>
