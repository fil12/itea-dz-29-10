<template>
        <div class="form-group">

            <input
                    :type="type"
                    :placeholder="placeholder"
                    :value="value"
                    :class = "NameClass"
                    @input="$emit('input', $event.target.value)"
            >
        </div>
</template>

<script>
    export default {
        name: "InputText",
        props:{
            type: String,
            placeholder: String,
            value: String,
            NameClass: String
        },

        data() {
            return {
                FormData: {

                }
            }
        }
    }
</script>

<style scoped>

</style>