<!--suppress ALL -->
<template>
    <div>

        <btn v-for="(tab, i) in tabs" :key="i" @customEvent="curTab = tab" @click="console.log(tab);">{{ tab }}</btn>
        <!--  keep-alive - когда vue отрендерит компонент, -->
        <!--  keep-alive его закеширует, что бы не тратить ресурс на следующую отрисовку  -->
        <keep-alive>
            <!--   тег component с привязкой отребута is дает возможность динамического использования компонентов   -->
            <component :is="curTab"></component>
        </keep-alive>
        <br><br><br>
    </div>
</template>

<script>
    import TabOne from './tabs/TabOne'
    import TabTwo from './tabs/TabTwo'
    import Btn from './Btn'

    export default {
        name: "Wrap",
        components: {
            TabOne,
            TabTwo,
            Btn
        },
        data() {
            return {
                tabs: [
                    "TabOne",
                    "TabTwo"
                ],
                curTab: 'tab-one'
            }
        }
    }

</script>

<style scoped>

</style>