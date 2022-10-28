<template>
  <Home />
</template>

<script>
import Home from "./components/Home.vue";

export default {
  name: "vueApp",
  components: { Home },
  methods: {},
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@300;400;500;700&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Oswald;
}

button {
  font-family: Oswald;
  font-weight: 700;
}
</style>
