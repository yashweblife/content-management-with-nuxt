<template>
    <div class="grid">
        <NuxtLink class="card" v-for="post in posts" :key="post.id" :to="`../posts/${''+post.id}`">
            <h2>
                {{ post.title }}
            </h2>
            <p>
                {{ post.body }}
            </p>
        </NuxtLink>
    </div>
</template>

<script lang="ts" setup>
import { AsyncData } from '#app';
const { id } = useRoute().params
type postData = {
    title: string,
    body: string,
    id: number,
}
const { data: posts } = await useFetch<postData[]>(`https://jsonplaceholder.typicode.com/posts?userId=${id}`)


</script>

<style lang="scss" scoped>
.grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 1em;
    align-items: center;
    justify-content: center;
    padding:3em;
    }

.card {
    padding: 1em;
    display: flex;
    flex-direction: column;
    box-shadow: 0 0 1em 0 rgba(0, 0, 0, 0.3);
    border-radius: 1em;
    width: 400px;
    >h2 {
        font-size: 1em;
    }
    >p{
        text-overflow: ellipsis;
        overflow: hidden;
        white-space: nowrap;
    }
}
</style>