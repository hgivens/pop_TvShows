<template>
    <div class="cardBody">
        <div class="card" style="width: 18rem;" v-for="tvShow in tvshowlist.slice(0,4)" v-bind:key="tvShow.id">
            <img v-bind:src="'https://image.tmdb.org/t/p/w500'+tvShow.poster_path" class="card-img-top" >
            <div class="card-body">
                <h5 class="card-title">{{tvShow.name}}</h5>
                <p class="card-text">{{tvShow.overview}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Card",
    props: ['tvshowlist'],
};
</script>

<style scoped>
    .cardBody{
        padding-left: 15%;
        padding-right: 15%;
        
    }
    .card{
        /* position: absolute; */
        display: inline-flex;
        margin: 10px;
        
    }

</style>