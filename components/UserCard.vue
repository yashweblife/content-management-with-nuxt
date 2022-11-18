<template>
    <NuxtLink class="card" :to="`users/${'' + user.id}`">
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
</template>

<script setup lang="ts">
const { user } = defineProps(["user"])
</script>

<style scoped>

</style>