<template>
  <div id="app">
    <app-header></app-header>

    <div class="container"> 

      <blog-card></blog-card>
      <blog-card></blog-card>
      <blog-card></blog-card>
      <blog-card></blog-card>
      
    </div>
  </div>
</template>

<script>
import AppHeader from './components/app-header'
import BlogCard from './components/blog-card'

export default {
  name: 'App',
  components: {
    AppHeader,
    BlogCard
  }
}
</script>

<style>

body{
  font-family: 'Lato', sans-serif;
  margin: 0;
}

.container{
  padding: 0 30px;
  max-width: 1024px;
  margin: auto;
  display: flex;
  flex-wrap:wrap ;

}
</style>
