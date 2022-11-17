<template>
    <div>
        <h2>Home</h2>
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Quaerat iusto animi amet est minima facilis
            excepturi repellat in corrupti nulla magni accusantium id dolorem eligendi dolores suscipit soluta
            doloremque, exercitationem facere quo ipsa ratione? Necessitatibus nostrum dolorem corrupti animi temporibus
            ab sed reiciendis nisi, esse labore odit atque vero. Recusandae quaerat, beatae maiores est dolor impedit
            modi culpa quas id corrupti architecto aliquam quos sed hic perferendis quam doloremque quisquam nam
            provident quo. Cum assumenda vel nisi obcaecati voluptates voluptatibus minima atque rem? Nesciunt,
            perferendis veniam numquam commodi, neque quibusdam asperiores fugit recusandae iusto itaque id distinctio
            porro reprehenderit doloribus.
        </p>
        <div class="grid">
            <NuxtLink class="card" v-for="user in users" :key="user.id" :to="`users/${''+   user.id}`">
                <div class="header">
                    <div class="image"></div>
                    <div class="name">
                        {{ user.name }}
                    </div>
                </div>
                <div class="content">
                    <div class="info">
                        <p>{{ user.company.name }}</p>
                        <p>{{ user.company.bs }}</p>
                    </div>
                </div>
            </NuxtLink>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { AsyncData } from "#app"

definePageMeta({
    layout: "default"
})
type apiRef = {
    name: string,
    id: number,
    company: {
        name: string,
        bs: string
    }
}
const { data: users } = await useFetch<apiRef[]>('https://jsonplaceholder.typicode.com/users')
</script>

<style lang="scss" scoped>
h2 {
    font-size: 1.5em;
    padding: 1em 2em;
}

p {
    padding: 0em 2em;
}

.grid {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 1em;
    padding:2em;
    >.card {
        display: flex;
        flex-direction: column;
        box-shadow: 0 0 1em 0 rgba(0,0,0,0.3);
        padding:1em;
        border-radius: 1em;
        .header{
            display: flex;
            align-items: center;
            margin-bottom: 1em;
            .image{
                width: 50px;
                aspect-ratio: 1/1;
                background-color: rgba(0,0,0,0.3);
                border-radius: 50%;
            }
            .name{
                margin-left: 2em;
            }
            font-size: 1.2em;
        }
    }
}
</style>