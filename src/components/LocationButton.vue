<template>
  <div>
    <button @click="getLocation">Get Location</button>
    <p v-if="errorMessage">{{ errorMessage }}</p>
    <p v-if="location">{{ location }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      location: null,
      errorMessage: null,
    };
  },
  methods: {
    getLocation() {
      if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(
          (position) => {
            this.location = `Latitude: ${position.coords.latitude}, Longitude: ${position.coords.longitude}`;
          },
          (error) => {
            this.errorMessage = error.message;
          }
        );
      } else {
        this.errorMessage = "Geolocation is not supported by this browser.";
      }
    },
  },
};
</script>
