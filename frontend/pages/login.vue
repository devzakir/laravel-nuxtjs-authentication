<template>
    <div class="row justify-content-center mt-5">
        <div class="col-6">
            <div class="card">
                <div class="card-header">
                    Login Page
                </div>
                <div class="card-body">
                    <form action="" @submit.prevent="userLogin">
                        <div class="form-group mb-3">
                            <label for="">Enter Email </label>
                            <input type="text" v-model="login.email" class="form-control" name="email" placeholder="Enter email">
                        </div>
                        <div class="form-group mb-3">
                            <label for="">Enter Password</label>
                            <input type="password" v-model="login.password" class="form-control" name="passwrd" placeholder="Enter password">
                        </div>
                        <div class="form-group d-flex justify-content-between align-items-center">
                            <button type="submit" class="btn btn-success">Give me Access</button>
                            <nuxt-link :to="{ name: 'register' }">Don't have account?</nuxt-link>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    auth: 'guest',
    data(){
        return {
            login: {
                email: 'web.zakirbd@gmail.com',
                password: 'password',
            }
        }
    },
    methods: {
        async userLogin() {
            try {
                let response = await this.$auth.loginWith('local', { data: this.login });

                console.log(response)
            } catch (err) {
                console.log(err)
            }
        }
    }
}
</script>

<style>

</style>
