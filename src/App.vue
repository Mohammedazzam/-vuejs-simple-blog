<template>
  <div id="app">
    <app-header></app-header>

    <div class="container" v-if="blogs"> 

      <blog-card
       v-for="blog in blogs" :key="blog.id"
       :data="blog"></blog-card>

    
    </div>

    <div class="text-center">
      <button
        type="button"
        class="load-more-button"
        @click="loadeMore"
        v-if="blogs && blogs.length < totalCount"
        >
      Load More
      </button>
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
      blogs:null,
      page:1,
      totalCount : null
    }
  },
  components: {
    AppHeader,
    BlogCard
  },

  mounted(){
    this.getBlogs(this.page);
  },

  methods:{
    getBlogs(page){
          axios.get(`http://localhost:3000/blog?_page=${page}&_limit=6`).then((res)=>{//('http://localhost:3000/blog')    ('http://localhost:3000/blog?_page=2&_limit=6')

      // console.log(res.data)
      this.blogs = this.blogs ? this.blogs.concat(res.data) : res.data;
      this.totalCount = res.headers['x-total-count'];
      // console.log(res.headers['x-total-count']);
    })
    },
    loadeMore(){
      this.page++;
      this.getBlogs(this.page)
    }
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
.text-center{
  text-align: center;
}
.load-more-button{
  color: #fff;
  background-color: #990099;
  border-radius: 5px;
  border: none;
  padding: 10px 25px;
  font-size: 18px;
  line-height: 1;
  margin-top: 50px;
  margin-bottom: 50px;
}
</style>
