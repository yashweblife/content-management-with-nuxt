<template>
    <div>
        <header>
            <h1>Nuxt Post</h1>
            <nav>
                <ul>
                    <li>
                        <NuxtLink to="/">Home</NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/about">About</NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/about">Users</NuxtLink>
                    </li>
                </ul>
            </nav>
        </header>
        <div>
            <slot />
        </div>
    </div>
</template>

<script setup lang="ts">

</script>

<style lang="scss">
* {
    font-family: Arial, Helvetica, sans-serif;
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

header {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1em 2em;

    >nav {
        width: 50%;

        >ul {
            display: flex;
            align-items: center;
            justify-content: space-between;

            >li {
                list-style-type: none;
            }
        }
    }
}

a {
    text-decoration: none;
    color: black;
}
</style>