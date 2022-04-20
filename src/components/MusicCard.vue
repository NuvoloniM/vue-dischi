<template>
<div class="card">
  <img :src="poster" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title"> {{title}} </h5>
    <p class="card-text"> {{author}} </p>
    <p class="card-text"> {{year}} </p>
  </div>
</div>
</template>

<script>
export default {
    name: 'MusicCard',
    props: {
        poster: String,
        year: String,
        title: String,
        author: String,
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/variables.scss';
    .card {
        flex-basis: calc( (100% / 5) - 20px);
        padding: 0;
        background: $primary-color;
        margin: 20px 10px;

        .card-body {
            padding: 10px;
            text-align: center;

            h5 {
                color: #fff;
            }
            p {
                color: #7c7976;
            }
        }
    }
</style>