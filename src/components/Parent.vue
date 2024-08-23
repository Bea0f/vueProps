<script setup lang="ts">
import { ref } from 'vue';
import { Person } from '../models/Person';
import Child from './Child.vue';

const person = ref<Person>(new Person("Beatrice", 26, 165));

const handleJump = (name:string) => {
    console.log(name, "hoppade");
    person.value.height += 0.5;
    
}
</script>

<template>

    <h3>Här visas innehållet från Parent: </h3>
    <Child :human="person" @jump="handleJump"/>



</template>


<style scoped></style>