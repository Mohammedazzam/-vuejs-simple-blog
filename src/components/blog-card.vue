<template>
    <div class="blog-card">

        <div class="card-image">
            <img src="../assets/blog-image.jpg" alt="artical title">
        </div>

        <div class="card-content">

            <h2 class="card-title">
                artical title
            </h2>

            <p class="card-summary">
                Sumary Hear  Sumary Hear Sumary Hear Sumary Hear Sumary Hear
            </p>

            <a href="" class="read-more">
                Continue reading
            </a>

        </div>
    </div>
</template>

<style lang="scss">
    .blog-card{
        box-sizing: border-box;
        padding: 30px 10px 0;

        width: 33%;
        @media(max-width: 900px) {
            width: 50%;
        }

        @media(max-width: 600px) {
            width: 100%;
        }
    }

    .card-image{
        img{
            width: 100%;
            border-radius: 5px;
        }
    }
    .card-title{
        color: #990099;
        font-size: 20px;
        font-weight: 700;
        margin-bottom: 7px;
    } 

    .card-summary{
        margin-top: 0;
        font-weight: 300;
        color: #333;
    } 

    .read-more{
        color: #333;
        font-size: 14px;
        font-weight: 400;
        font-style: italic;
    }

</style>

<script>
export default {
    
}
</script>