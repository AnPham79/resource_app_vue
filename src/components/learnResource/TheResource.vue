<template>
  <base-card>
    <base-button @click="setSelectedTab('StoreResouce')" :mode='storedResButtonMode'>Stored Resource</base-button>
    <base-button @click="setSelectedTab('AddResource')" :mode="addResButtonMode">Add Resource</base-button>
  </base-card>
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import StoreResouce from './StoreResouce.vue';
import AddResource from './AddResource.vue';

export default {
  components: {
    StoreResouce,
    AddResource,
  },
  data() {
    return {
      selectedTab: 'StoreResouce',
      storeResource: [
        {
          id: 1,
          title: 'Learn JavaScript',
          description: 'An online course to learn JavaScript from basics to advanced topics.',
          link: 'https://www.learnjavascript.com',
        },
        {
          id: 2,
          title: 'Master PHP',
          description: 'A comprehensive guide to becoming a PHP master, including advanced techniques.',
          link: 'https://www.masterphp.com',
        },
        {
          id: 3,
          title: 'CSS Tricks',
          description: 'A resource for learning and mastering CSS with practical examples and tips.',
          link: 'https://www.csstricks.com',
        },
        {
          id: 4,
          title: 'Laravel for Beginners',
          description: 'An introduction to Laravel framework for PHP developers, with hands-on projects.',
          link: 'https://www.laravelforbeginners.com',
        },
        {
          id: 5,
          title: 'Vue.js Essentials',
          description: 'Learn the essentials of Vue.js, a popular JavaScript framework for building user interfaces.',
          link: 'https://www.vuejsessentials.com',
        },
      ],
    };
  },
  provide() {
    return {
      resources: this.storeResource,
      addResource: this.addResource,
      destroyResource: this.removeResource
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, description, url) {
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        url: url
      };
      this.storeResource.unshift(newResource);
      this.selectedTab = 'StoreResouce';
    },
    removeResource(resId) {
      const resIndex = this.storeResource.findIndex(res => res.id == resId);
      this.storeResource.splice(resIndex, 1);
    }
  },
  computed: {
    storedResButtonMode() {
      return this.selectedTab === 'StoreResouce' ? 'null' : 'flat';
    },
    addResButtonMode() {
      return this.selectedTab === 'AddResource' ? 'null' : 'flat';
    }
  }
};
</script>
