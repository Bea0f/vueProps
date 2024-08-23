<script setup lang="ts">
import { ref } from 'vue';
import { IMovie } from '../models/IMovie';


interface IMovieProps {
    movie: IMovie;
}

const props = defineProps<IMovieProps>();

const movieUrl = ref<string>(props.movie.Poster);

</script>

<template>
    <div class="movie">
        <h2>{{ props.movie.Title}}</h2>
        <h3>{{ props.movie.Year }}</h3>
        <img :src="movieUrl" alt="">
    </div>
</template>

<style scoped></style>