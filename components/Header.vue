<template>
    <header>
        <h1>
            Nuxty Vue Posts | {{ title }}
        </h1>
        <nav>
            <ul>
                <li>
                    <NuxtLink to="/">Home</NuxtLink>
                    <div class="slider"></div>
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
const { title } = defineProps(['title'])
</script>

<style lang="scss" scoped>
header {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: column;
    padding: 1em 2em;

    >nav {
        width: 100%;
        margin-top: 2em;
        padding:0 2em;
        >ul {
            display: flex;
            align-items: center;
            justify-content: space-between;

            >li {
                list-style-type: none;
                position: relative;
                >.slider{
                    position: absolute;
                    width:100%;
                    height:0.2em;
                    background-color: rgb(0, 225, 255);
                }
            }
        }
    }
}

@media screen and (min-width: 800px) {
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
}
</style>