<template>
    <div id="app">
        <Wrap></Wrap>

    </div>
</template>

<script>

    import Wrap from './components/Wrap'

    export default {
        name: 'app',
        components: {
            Wrap
        }
    }
</script>

<style lang="scss">
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
