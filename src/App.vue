<template>
  <div id="app">
    <app-header></app-header>
  </div>
</template>

<script>
import AppHeader from './components/app-header'

export default {
  name: 'App',
  components: {
    AppHeader
  }
}
</script>

<style>
body{
  margin: 0;
}
</style>
