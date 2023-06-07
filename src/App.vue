<template>
  <div id="app">
    <LocationButton />
  </div>
</template>

<script>
import LocationButton from "./components/LocationButton.vue";

export default {
  name: "App",
  components: {
    LocationButton,
  },
};
</script>

<style>
#app {
  text-align: center;
  padding: 100px;
}
</style>
