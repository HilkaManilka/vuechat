<template>
  <div id="app">
    <app-header></app-header>
  </div>
</template>

<script>
import AppHeader from './components/layouts/Header.vue'

export default {
  name: 'app',
  components: {
      AppHeader
  }
}
</script>

<style>
#app {

}
</style>