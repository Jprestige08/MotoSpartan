<template>
    <div>
      <!-- Componente compuesto por otros componentes -->
      <h3>Nested Component</h3>
      <Home />
      <About />
    </div>
  </template>

<script>
import Home from './HomePage.vue'
import About from './AboutSection.vue'

export default {
  name: 'NestedComponent',
  components: {
    Home,
    About
  }
}
</script>
