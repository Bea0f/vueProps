<script setup lang="ts">
import { onMounted, ref } from 'vue';
import { IMovie } from '../models/IMovie';
import { IOmbdResponse } from '../models/IOmbdResponse';
import Movie from './Movie.vue';

const movies = ref<IMovie[]>([]);

onMounted(async () => {
    const response = await fetch("https://omdbapi.com/?apikey=6ffecd8b&s=star");
    if (!response.ok) {
    }
    const data: IOmbdResponse = await response.json();
    movies.value = data.Search;
})

const handleBuy = (id:string) => {

    const foundMovie = movies.value.find((m) => m.imbdID === id);

    console.log("Du klickade på:", foundMovie?.Title);
}
</script>

<template>
    <div class="movies">
        <!--Hämta från child??-->
        <Movie v-for="m in movies" :movies="movie" :key="movie.imbdID"/>
    </div>
</template>

<style scoped></style>