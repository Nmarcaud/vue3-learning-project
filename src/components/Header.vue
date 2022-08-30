<template>
    <header>
        <!-- As a link -->
        <nav class="navbar navbar-expand-lg navbar-dark bg-green">
            <div class="container-fluid">
                
                <a class="navbar-brand" href="#">
                    <img src="../assets/logo.svg" alt="" class="logo">
                    <span class="logo-text">Le shop Vue de Nico</span>
                </a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                
                <div class="collapse navbar-collapse d-flex justify-content-between" id="navbarNavDropdown">
                    <ul class="navbar-nav">
                        <li class="nav-item">
                            <a class="nav-link" href="#">Boutique</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#">Admin</a>
                        </li>
                    </ul>
                    <ul class="navbar-nav">
                        <li class="nav-item">
                            <a class="nav-link" href="#">Inscription</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#">Connexion</a>
                        </li>
                    </ul>
                </div>

            </div>
        </nav>
    </header>
</template>


<script setup lang="ts">

</script>


<style lang="scss" scoped>
    .logo {
        width: 20px;
        margin-right: .5rem;

        &-text{
            font-weight: 600;
        }
    }
</style>
