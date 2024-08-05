<template>
  <div>
    <StoreResource :resources="storeResource"></StoreResource>
  </div>
</template>

<script>
import StoreResource from './components/StoreResouce.vue';

export default {
  components: {
    StoreResource
  },
  data() {
    return {
      storeResource: [
        {
          id: 1,
          title: "Learn JavaScript",
          description: "An online course to learn JavaScript from basics to advanced topics.",
          link: "https://www.learnjavascript.com"
        },
        {
          id: 2,
          title: "Master PHP",
          description: "A comprehensive guide to becoming a PHP master, including advanced techniques.",
          link: "https://www.masterphp.com"
        },
        {
          id: 3,
          title: "CSS Tricks",
          description: "A resource for learning and mastering CSS with practical examples and tips.",
          link: "https://www.csstricks.com"
        },
        {
          id: 4,
          title: "Laravel for Beginners",
          description: "An introduction to Laravel framework for PHP developers, with hands-on projects.",
          link: "https://www.laravelforbeginners.com"
        },
        {
          id: 5,
          title: "Vue.js Essentials",
          description: "Learn the essentials of Vue.js, a popular JavaScript framework for building user interfaces.",
          link: "https://www.vuejsessentials.com"
        }
      ]
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
