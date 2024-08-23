<script setup lang="ts">
import { Person } from '../models/Person';

interface ChildProps {
    human: Person;
}

const props = defineProps<ChildProps>();

console.log(props.human.age);

const emit = defineEmits<{
    (e: "jump", name: string): void;
}>();

const handleClick = () => {
    emit("jump", props.human.name);
}

</script>

<template>

    <h5>Här visas innehållet från Child: {{ human.height }}</h5>

    <button @click="handleClick"> {{ human.name }}</button>

</template>


<style scoped></style>