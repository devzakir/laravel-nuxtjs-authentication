<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
      <div class="container">
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <nuxt-link class="nav-link active" :to="{ name: 'index' }">Home</nuxt-link>
            </li>
            <li class="nav-item">
              <nuxt-link class="nav-link" :to="{ name: 'login' }">Login Page</nuxt-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <div class="container mt-3">
        <Nuxt />
    </div>
  </div>
</template>

<style>
  @import url('https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta3/dist/css/bootstrap.min.css');

</style>
