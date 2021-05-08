<template>
  <div>
      <div class="card">
          <div class="card-header">
              Welcome to our website
          </div>
          <div class="card-body py-5 text-center">
              <h4 v-if="loggedIn">Welcome, {{ user.name }}</h4>
              <div class="text-center mb-4">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Enim, odit? Quibusdam exercitationem veritatis eveniet, animi fuga fugiat maxime similique. Maiores itaque corrupti nulla blanditiis repellat voluptas iure at enim nobis?
              </div>
              <div class="text-center">
                  <nuxt-link :to="{ name: 'dashboard' }" class="btn btn-primary">Go to Dashboard</nuxt-link>
                  <nuxt-link :to="{ name: 'register' }" class="btn btn-success">Sign Up</nuxt-link>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    computed: {
        loggedIn(){
            return this.$store.state.auth.loggedIn;
        },
        user(){
            return this.$store.state.auth.user
        }
    }
}
</script>

<style>

</style>
