<template>
    <!-- к обьекту события можно получить доступ через $event  -->
    <button :type="type" @click="clickHandler($event, 1)" class="btn">{{ label }}</button>

</template>

<script>
    export default {
        name: "Btn",
        props: {
            label: {
                type: String,
                default: 'Click me'
            },
            type: {
                type: String,
                default: `button`
            }
        },
        data() {
            return {
                msgForParent: 'Called parent event handler'
            }
        },
        methods: {
            clickHandler(e, par) {
                const self = this;
                self.$emit('customEvent', self.msgForParent)
            }
        }
    }
</script>

<style lang="sass">
</style>


