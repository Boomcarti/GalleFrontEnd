<template>
  <router-view/>
</template>

<script>

export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}

html, body {
  margin: 0;
  padding: 0;
  height: 100%;
}

/* Ensure #app takes full height and has no padding/margins */
#app {

  min-height: 100vh; /* Full viewport height */
}

</style>
