<template>
    <li>
        {{ title }}
        <button v-on:click="$emit('remove')">X</button>
    </li>
</template>

<script>
    export default {
        name: "TodoItem",
        props: {
            title: {
                type: String,
                required: true
            }
        }
    }
</script>

<style scoped>

</style>