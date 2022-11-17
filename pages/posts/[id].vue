<template>
    <div>
        <details class="card">
            <summary class="header">
                <h2>
                    {{post.title}}
                </h2>
                <p>
                    {{post.body}}
                </p>
            </summary>
            <div class="content">
                <h4>Comments</h4>
                <div class="card" v-for="comment in comments" :key="comment.id">
                    <div class="header">
                        <div class="image"></div>
                        <div class="name">{{comment.email}}</div>
                    </div>
                    <div class="content">
                        <h4>
                            {{comment.name}}
                        </h4>
                        <p>
                            {{comment.body}}
                        </p>
                    </div>
                </div>
            </div>
        </details>
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
    body:string,
    email:string
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
    width:50%;
    >summary.header{
        margin-bottom:1em;
    }
    >div.header{
        display:flex;
        align-items: center;
        >.name{
            margin-left: 2em;
        }
        >.image{
            width:50px;
            aspect-ratio: 1/1;
            border-radius: 50%;
            background-color: rgba(0,0,0,0.5);
        }
    }
    }
</style>