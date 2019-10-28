<template>
        <div class="form-group">
            <input
                    :type="type"
                    :placeholder="placeholder"
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
            NameClass: {type: String, default: `form-control`}
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