<template>
    <div v-if="blog">
    <app-header>
      <h1>
        {{blog.title}}
      </h1>
    </app-header>
    </div>
</template>

<script>

import AppHeader from '../components/app-header'
import axios from 'axios';

export default {
    components:{
        AppHeader
    },
    data(){
        return{
            blog:null
        }
    },
    mounted(){
        axios.get('http://localhost:3000/blog/'+this.$route.params.id).then((res) => {
            // console.log(res.data)
            this.blog = res.data;
            
        });

    }
}
</script>



<style lang="">
    
</style>