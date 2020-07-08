<template>
  <div id="app">
    <app-header></app-header>

    <div class="container" v-if="blogs"> 

      <blog-card
       v-for="blog in blogs" :key="blog.id"
       :data="blog"></blog-card>


    </div>
  </div>
</template>

<script>
import AppHeader from './components/app-header'
import BlogCard from './components/blog-card'
import axios from'axios'

export default {
  name: 'App',
  data(){
    return{
      blogs:null
    }
  },
  components: {
    AppHeader,
    BlogCard
  },
  mounted(){
    axios.get('http://localhost:3000/blog?_page=1&_limit=6').then((res)=>{//('http://localhost:3000/blog')    ('http://localhost:3000/blog?_page=2&_limit=6')

      // console.log(res.data)
      this.blogs = res.data
    })
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
