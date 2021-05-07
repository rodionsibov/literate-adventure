<template>
  <header>
    <navbar />
  </header>
</template>

<script>
import Navbar from "./components/Navbar.vue";

export default {
  components: { Navbar },
  name: "App",
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

header {
  width: 100vw;
  background-color: #222;
  padding: 15px;
}

@media (max-width: 400px) {
  body {
    font-size: 14px;
  }
}
</style>
