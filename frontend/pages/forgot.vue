<template>
    <div class="row justify-content-center mt-5">
        <div class="col-6">
            <div class="card">
                <div class="card-header">
                    Forgot Password
                </div>
                <div class="card-body">
                    <form @submit.prevent="sendPasswordResetEmail" @keydown="forgotPassword.onKeydown($event)">
                        <div class="form-group mb-3">
                            <label for="">Enter Email </label>
                            <input type="text" v-model="forgotPassword.email" class="form-control" name="email" placeholder="Enter email" :class="{ 'is-invalid': forgotPassword.errors.has('email') }">
                            <has-error :form="forgotPassword" field="email"></has-error>
                        </div>
                        <div class="form-group d-flex justify-content-between align-items-center">
                            <button :disabled="forgotPassword.busy" type="submit" class="btn btn-success">
                                Send Password Reset Email
                            </button>
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
            forgotPassword: this.$vform({
                email: '',
            }),
        }
    },
    methods: {
        async sendPasswordResetEmail() {
            try {
                let { data } = await this.forgotPassword.post('/auth/password/email');

                this.$toast.success({
                    title: 'Success!',
                    message: 'Reset password email has been sent',
                })
            } catch (err) {
                console.log(err)
            }
        }
    }
}
</script>

<style>

</style>
