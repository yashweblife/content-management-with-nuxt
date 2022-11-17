<template>
    <header>
        <h1>
            Nuxt Posts | {{title}}
        </h1>
        <nav>
            <ul>
                <li>
                    <NuxtLink to="/">Home</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/about">About</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/users">Users</NuxtLink>
                </li>
            </ul>
        </nav>
    </header>
</template>

<script setup lang="ts">
    const {title} = defineProps(['title'])
</script>

<style scoped>

</style>