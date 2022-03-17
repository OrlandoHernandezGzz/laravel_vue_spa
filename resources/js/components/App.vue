<template>
  <main>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <div class="container-fluid">
            <!-- <a class="navbar-brand" href="#">CRUD</a> -->
            <router-link exact-active-class="active" to="/" class="nav-link active">Inicio</router-link>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
                <div class="navbar-nav">
                    <router-link exact-active-class="active" to="/blogs" class="nav-link active">Blogs</router-link>
                    <router-link exact-active-class="active" to="/contacto" class="nav-link active">Contacto</router-link>
                    <!-- <a class="nav-link active" aria-current="page" href="#">Blogs</a> -->
                    <!-- <a class="nav-link" href="#">Contacto</a> -->
                </div>
            </div>
        </div>
    </nav>

    <div>
        <!-- Mostrar las vistas -->
        <router-view></router-view>
    </div>
  </main>
</template>

<script>
export default {

}
</script>

<style>

</style>