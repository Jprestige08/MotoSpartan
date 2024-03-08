<template>
  <div>
    <h1>Imágenes de Motos</h1>
    <div class="motorcycle-images">
      <img v-for="photo in motorcyclePhotos" :key="photo.id" :src="photo.src.small" alt="Imagen de moto" />
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'ApiComponent',
  data() {
    return {
      motorcyclePhotos: [],
    };
  },
  created() {
    // Reemplaza 'YOUR_API_KEY' con tu propia clave de API de Pexels
    const apiKey = 'lhXOzdWpnm6SCuLEeQAgjy4hJPO3lmanOBrFqSOvOwMjViBrN9i4te2g';

    axios.get('https://api.pexels.com/v1/search', {
      params: {
        query: 'motorcycle',
        per_page: 10, // Número de imágenes que deseas obtener
      },
      headers: {
        Authorization: apiKey,
      },
    })
      .then((response) => {
        this.motorcyclePhotos = response.data.photos;
      })
      .catch((error) => {
        console.error('Error al cargar imágenes de motos', error);
      });
  },
};
</script>
