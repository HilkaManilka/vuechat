<template>
  <v-app>
    <app-header></app-header>
    <v-layout flex>
      <side-bar-menu></side-bar-menu>
      <dialog-list></dialog-list>
    </v-layout>
  </v-app>
</template>

<script>
import AppHeader from './components/layouts/Header.vue';
import DialogList from './components/DialogList.vue';
import SideBarMenu from './components/layouts/Sidebar.vue';

export default {
  name: 'app',
  components: {
      AppHeader,
      DialogList,
      SideBarMenu
  },
  mounted: {

  },
  data() {

  },
  methods: {
    debug: (data) => {
        console.log(data);
    }
  }
}
</script>

<style>
#app {

}
</style>