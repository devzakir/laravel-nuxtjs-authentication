<template>
    <div class="row justify-content-center mt-5">
        <div class="col-6">
            <div class="card">
                <div class="card-header">
                    Create an account
                </div>
                <div class="card-body">
                    <form action="" @submit.prevent="registerUser">
                        <div class="form-group mb-3">
                            <label for="">Your name </label>
                            <input type="text" v-model="registerForm.name" class="form-control" name="email" placeholder="Enter email">
                        </div>
                        <div class="form-group mb-3">
                            <label for="">Your email </label>
                            <input type="text" v-model="registerForm.email" class="form-control" name="email" placeholder="Enter email">
                        </div>
                        <div class="form-group mb-3">
                            <label for="">Your Password</label>
                            <input type="password" v-model="registerForm.password" class="form-control" name="passwrd" placeholder="Enter password">
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
    auth: 'guest',
    data(){
        return {
            registerForm: {
                name: '',
                email: '',
                password: '',
            }
        }
    },
    methods: {
        async registerUser() {
            try {
                // let response = ;

                // console.log(response)
            } catch (err) {
                console.log(err)
            }
        }
    }
}
</script>

<style>

</style>
