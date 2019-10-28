<template>
    <div class="container">
        <header>
            <slot name="title">
                <h1>default content for Title</h1>
            </slot>
        </header>
        <main>
            <slot name="input" :add="todoList">
                <h2>default content for MIDDLE</h2>
            </slot>
        </main>
    </div>
</template>

<script>
    export default {
        name: "ToDos",
        data() {
            return {
                todoList: {
                    name: 'Sasha',
                }
            }
        }
    }
</script>

<style scoped>

</style>