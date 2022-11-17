<template>
    <div>
        <Header title="V0.0.1"/>
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