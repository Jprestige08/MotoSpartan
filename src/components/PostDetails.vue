<template>
    <div>
      <h2>Detalles de la Publicación</h2>
      <div class="card">
        <div class="card-body">
          <h5 class="card-title">{{ post.title }}</h5>
          <p class="card-text">{{ post.content }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        post: null, // Aquí almacenarás los detalles de la publicación
      };
    },
    created() {
      // Aquí debes cargar los detalles de la publicación utilizando el ID pasado en la URL
      const postId = this.$route.params.id; // Obtén el ID de la URL
      // Realiza una solicitud HTTP para obtener los detalles de la publicación
      // Asigna los detalles de la publicación a this.post
    },
  };
  </script>
  