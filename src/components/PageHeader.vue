<template>
  <div>
    <v-app-bar app color="#a7d5e1">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="d-md-none"></v-app-bar-nav-icon>
      <v-app-bar-title>
        <router-link to="/" class="text-decoration-none white--text">Then Eden?</router-link>
      </v-app-bar-title>

      <v-spacer></v-spacer>

      <!-- nav for large screens -->
      <v-btn text class="d-none d-md-inline-block" @click="scrollTo('#intro')">Home</v-btn>
      <v-btn text class="d-none d-md-inline-block" @click="scrollTo('#index')">About</v-btn>
      <v-btn text class="d-none d-md-inline-block" @click="scrollTo('#portfolio')">Portfolio</v-btn>
      <v-btn text class="d-none d-md-inline-block" @click="scrollTo('#service')">Services</v-btn>
      <v-btn text class="d-none d-md-inline-block" @click="scrollTo('#hireme')">Get in contact</v-btn>
    </v-app-bar>

    <!-- burger menu for small screens-->
    <v-navigation-drawer
      v-model="drawer"
      app
      temporary
      right
      class="d-md-none"
    >
      <v-list nav dense>
        <v-list-item v-for="(item, index) in menuItems" :key="index" link @click="handleItemClick(item.section)">
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: 'PageHeader',
  data() {
    return {
      drawer: false,
      menuItems: [
        { title: 'Home', section: '#intro' },
        { title: 'About', section: '#index' },
        { title: 'Portfolio', section: '#portfolio' },
        { title: 'Services', section: '#service' },
        { title: 'Get in contact', section: '#hireme' }
      ]
    };
  },
  methods: {
    scrollTo(section) {
      const element = document.querySelector(section);
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
      }
    },
    handleItemClick(section) {
      this.scrollTo(section);
      this.drawer = false;
    }
  }
};
</script>

<style scoped>
* {
  color: white;
}

.v-app-bar {
  background-color: #a7d5e1 !important;
}

.v-app-bar-title {
  font-weight: bold;
  margin-left: 10px;
}

.v-btn {
  margin-right: 10px;
  color: white;
}

.v-navigation-drawer {
  background-color: white !important; 
}

.v-list-item-title {
  color: #a7d5e1 !important; 
}

</style>
