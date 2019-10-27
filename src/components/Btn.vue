<template>
    <!-- к обьекту события можно получить доступ через $event  -->
    <button type="button" @click="clickHandler($event, 1)" class="btn">{{ label }}</button>

</template>

<script>
    export default {
        name: "Btn",
        props: {
            label: {
                type: String,
                default: 'Click me'
            }
        },
        data() {
            return {
                msgForParent: 'Called parent event handler'
            }
        },
        methods: {
            clickHandler(e, par) {
                console.log(e);
                console.log(par);
                console.log('Inside the Btn component - called self handler');
                const self = this;
                self.$emit('customEvent', self.msgForParent)
                // setTimeout(() => self.$emit('customEvent', self.msgForParent), 500)
            }
        }
    }
</script>

<style lang="sass">
</style>


