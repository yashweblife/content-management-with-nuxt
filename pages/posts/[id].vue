<template>
    <div>
        <div class="card">
            <div class="header">
                <h2>
                    {{post.title}}
                </h2>
                <p>
                    {{post.body}}
                </p>
            </div>
            <div class="content">
                <div class="card" v-for="comment in comments" :key="comment.id">
                    <div class="header">
                        {{comment.name}}
                    </div>
                    <div class="content">
                        {{comment.body}}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import { AsyncData } from '#app';
const { id } = useRoute().params
definePageMeta({
    layout:"default"
})
console.log(id)
type postData = {
    title: string,
    body: string,
    id: number,
}
type commentData = {
    id:number,
    name:string,
    body:string
}
const {data:post}= await useFetch<postData>(`https://jsonplaceholder.typicode.com/posts/${id}`)
const {data:comments}= await useFetch<commentData[]>(`https://jsonplaceholder.typicode.com/comments?postId=${id}`)
</script>

<style lang="scss" scoped>
.card{
    padding:1em;
    border-radius: 0.5em;
    box-shadow: 0 0 1em 0 rgba(0,0,0,0.5);
    margin:1em;
    }
</style>