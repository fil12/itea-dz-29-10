<!--suppress ALL -->
<template>
    <div>
        <div class="container">
            <div class="row">
                <div class="col-md-6 col-md-offset-3">
                    <div class="panel panel-login">
                        <div class="panel-heading">
                            <div class="row">
                                <div class="col-xs-6" >
                                    <btn v-for="(tab, i) in tabs" :label="tab.label" :key="i" @customEvent="curTab = tab" >{{ tab.name }}</btn>
                                </div>
                            </div>
                            <hr>
                        </div>
                        <div class="panel-body">
                            <div class="row">
                                <div class="col-lg-12">
                                    <keep-alive>
                                        <component :is="curTab.name"></component>
                                    </keep-alive>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
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
                    {
                        name: `TabOne`,
                        label: `Login Form`
                    },
                    {
                        name: `TabTwo`,
                        label: `Registration Form`
                    }
                ],
                curTab: {name:`TabOne`, label: `Login Form`}
            }
        }
    }

</script>

<style scoped lang="css">


</style>