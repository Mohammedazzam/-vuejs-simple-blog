<template>
    <div v-if="blog">
        <p>{{blog.title}}</p>
    </div>
</template>

<script>
import axios from 'axios';
export default {
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