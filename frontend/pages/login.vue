<template>
    <div class="row justify-content-center mt-5">
        <div class="col-6">
            <div class="card">
                <div class="card-header">
                    Login Page
                </div>
                <div class="card-body">
                    <div class="alert alert-danger" v-if="loginForm.errors.errors.account">
                        {{ loginForm.errors.errors.account[0] }}
                    </div>
                    <form @submit.prevent="userLogin" @keydown="loginForm.onKeydown($event)">
                        <div class="form-group mb-3">
                            <label for="">Enter Email </label>
                            <input type="text" v-model="loginForm.email" class="form-control" name="email" placeholder="Enter email" :class="{ 'is-invalid': loginForm.errors.has('email') }">
                            <has-error :form="loginForm" field="email"></has-error>
                        </div>
                        <div class="form-group mb-3">
                            <label for="">Enter Password</label>
                            <input type="password" v-model="loginForm.password" class="form-control" name="passwrd" placeholder="Enter password" :class="{ 'is-invalid': loginForm.errors.has('password') }">
                            <has-error :form="loginForm" field="password"></has-error>
                        </div>
                        <div class="form-group d-flex justify-content-between align-items-center">
                            <button :disabled="loginForm.busy" type="submit" class="btn btn-success">Give me Access</button>
                            <nuxt-link :to="{ name: 'register' }">Don't have account?</nuxt-link>
                        </div>
                        <div class="mt-3">
                            <nuxt-link :to="{ name: 'forgot' }">Forgot Password? </nuxt-link>
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
            loginForm: this.$vform({
                email: 'web.zakirbd@gmail.com',
                password: 'password',
            }),
        }
    },
    methods: {
        async userLogin() {
            try {
                let { data } = await this.loginForm.post('/auth/login');
                await this.$auth.setUserToken(data.access_token);

                this.$toast.success({
                    title: 'Success!',
                    message: 'Welcome to our app',
                })
                
                this.loginForm.reset();
            } catch (err) {
                console.log(err)
            }
        }
    }
}
</script>

<style>

</style>
