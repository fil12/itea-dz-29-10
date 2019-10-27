<template>
    <div>
        <div v-if="!RegFormSubmited">
            <form id="register-form" role="form" @submit="submit">
                <div class="form-group">
                    <input-text
                            v-model="RegForm.name"
                            type="text"
                            id="user_name"
                            name="name"
                            name-class="form-control"
                            placeholder="Username"
                    />
                </div>
                <div class="form-group">
                    <input-text
                            v-model="RegForm.email"
                            type="email"
                            id="email"
                            name="email"
                            name-class="form-control"
                            placeholder="Email"
                    />
                </div>
                <div class="form-group">
                    <input-text
                            v-model="RegForm.pass"
                            type="password"
                            id="pass"
                            name="pass"
                            name-class="form-control"
                            placeholder="Password"
                    />
                </div>
                <div class="form-group">
                    <input-text
                            v-model="RegForm.passConfirm"
                            type="password"
                            id="passConfirm"
                            name="passConfirm"
                            name-class="form-control"
                            placeholder="Password Confirmation"
                    />
                </div>
                <div class="form-group">
                    <div class="row">
                        <div class="col-sm-6 col-sm-offset-3">
                            <input type="submit" name="register-submit" id="register-submit" tabindex="4"
                                   class="form-control btn btn-register" value="Register Now">
                        </div>
                    </div>
                </div>
            </form>
        </div>
        <div v-else>
            <h3>Вы зарегистрировались под именем <strong>"{{RegForm.name}}"</strong></h3>
        </div>

    </div>

</template>

<script>
    import InputText from "../inputs/InputText";

    export default {
        name: "TabTwo",
        components: {
            InputText
        },
        data() {
            return {
                RegForm: {
                    name: null,
                    email: null,
                    pass: null,
                    passConfirm: null
                },
                RegFormSubmited: false
            }
        },
        methods: {
            submit() {
                if (
                    !this.RegForm.name ||
                    !this.RegForm.pass ||
                    !this.RegForm.email ||
                    !this.RegForm.passConfirm
                ) {
                    return;
                }
                this.RegFormSubmited = true;
                console.log(this.RegFormSubmited);
            }
        }
    }
</script>

<style scoped lang="css">

</style>