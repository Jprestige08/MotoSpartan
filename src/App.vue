<template>
  <div>
    <header class="bg-dark text-light py-3"> 
      <div class="container">
        <h1 class="text-light">MotoSpartan</h1>
      </div>
    </header>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container">
        <router-link to="/" class="navbar-brand">INICIO</router-link>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <router-link to="/about" class="nav-link">SOBRE NOSOTROS</router-link>
            </li>
            <li class="nav-item">
              <router-link to="/contact" class="nav-link">CONOCE TU MOTO</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
   <RouterView></RouterView>
  </div>
</template>


