<template>
  <div>
    <TheHeader title="RememberMe"></TheHeader>
    <TheResource :resources="storeResource"></TheResource>
  </div>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheResource from './components/learnResource/TheResource.vue';

export default {
  components: {
    TheHeader,
    TheResource
  },
  data() {
    return {
      
    }
  }
}
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
