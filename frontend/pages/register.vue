<template>
    <div class="row justify-content-center mt-5">
        <div class="col-6">
            <div class="card">
                <div class="card-header">
                    Create an account
                </div>
                <div class="card-body">
                    <form action="" @submit.prevent="userLogin">
                        <div class="form-group mb-3">
                            <label for="">Your name </label>
                            <input type="text" class="form-control" name="email" placeholder="Enter email">
                        </div>
                        <div class="form-group mb-3">
                            <label for="">Your email </label>
                            <input type="text" class="form-control" name="email" placeholder="Enter email">
                        </div>
                        <div class="form-group mb-3">
                            <label for="">Your Password</label>
                            <input type="password" class="form-control" name="passwrd" placeholder="Enter password">
                        </div>
                        <div class="form-group d-flex justify-content-between align-items-center">
                            <button type="submit" class="btn btn-success">Create an account</button>
                            <nuxt-link :to="{ name: 'login' }">Account Login</nuxt-link>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
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
