<template>
  <div>
    <div class="main-container">
      <div class="container mt-4">
        <!-- Título y descripción -->
        <div class="card mb-4 bg-dark">
          <div class="card-body">
            <h2 class="card-text text-light">
              Bienvenidos a Motospartan: Donde la Pasión por las Motos se Hace
              Realidad
            </h2>
            <p class="card-text text-light">
              En Motospartan, no solo vendemos motos, ¡hacemos realidad tus
              sueños sobre dos ruedas! Somos mucho más que una tienda de motos;
              somos apasionados amantes de la velocidad, la libertad y la
              emoción que solo una moto puede ofrecer.
            </p>
          </div>
        </div>
        <div class="card mb-4 bg-dark">
          <div class="card-body">
            <p class="card-text text-light">
              Nuestro compromiso es brindarte la experiencia de conducción
              perfecta, sin importar si eres un novato entusiasmado o un
              veterano experimentado. Ofrecemos una amplia gama de motos, desde
              las clásicas y elegantes hasta las más modernas y deportivas, para
              satisfacer todos los gustos y necesidades.
            </p>
          </div>
        </div>
        <div class="card mb-4 bg-dark">
          <div class="card-body">
            <p class="card-text text-light">
              En Motospartan, no solo te ofrecemos motos excepcionales, sino
              también:
            </p>
            <ul class="text-light">
              <li>
                Asesoramiento experto para ayudarte a encontrar la moto
                perfecta.
              </li>
              <li>
                Servicios de mantenimiento y reparación de alta calidad para
                mantener tu moto en su mejor forma.
              </li>
              <li>
                Accesorios y equipamiento de seguridad de vanguardia para que
                puedas disfrutar de cada viaje con tranquilidad.
              </li>
              <li>
                Comunidad de entusiastas de las motos con eventos y actividades
                para compartir tu pasión.
              </li>
            </ul>
          </div>
        </div>
        <div class="card mb-4 bg-dark">
          <div class="card-body">
            <p class="card-text text-light">
              Entra en el mundo de Motospartan y descubre una nueva dimensión de
              aventura sobre dos ruedas. Únete a nuestra comunidad de
              apasionados motociclistas y experimenta la libertad, la emoción y
              la adrenalina que solo una moto puede ofrecer.
            </p>
          </div>
        </div>
        <div class="card mb-4 bg-dark">
          <div class="card-body">
            <p class="card-text text-light">
              Tu viaje comienza aquí. ¡Bienvenido a Motospartan!
            </p>
          </div>
        </div>
        <!-- Tarjetas -->
        <div class="row">
          <div class="col-md-4" v-for="post in posts" :key="post.id">
            <div class="card mb-4">
              <img
                v-if="post.image"
                :src="post.image"
                class="card-img-top"
                alt="Imagen de la moto"
              />
              <div class="card-body">
                <h5 class="card-title">{{ post.title }}</h5>
                <p class="card-text text-dark">{{ post.content }}</p> <!-- Cambiado a text-dark -->
              
              </div>
            </div>
          </div>
          <!-- Tarjeta 3 -->
          <div class="col-md-4">
            <div class="card mb-4">
              <img
                v-if="post3.image"
                :src="post3.image"
                class="card-img-top"
                alt="Imagen de la moto"
              />
              <div class="card-body">
                <h5 class="card-title">{{ post3.title }}</h5>
                <p class="card-text text-dark">{{ post3.content }}</p> <!-- Cambiado a text-dark -->
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "Aventura Todo Terreno",
          content:
            "¿Listo para la aventura? Nuestra moto todo terreno es tu mejor compañera en rutas off-road. Conquista cualquier terreno",
        },
        {
          id: 2,
          title: "Moto Clásica de Estilo Vintage",
          content:
            "Viaja en el tiempo con nuestra moto clásic a de estilo vintage. Un homenaje a la elegancia y la tradición en dos ruedas.",
        },
      ],
      post3: {
        id: 3,
        title: "Moto Deportiva de Alto Rendimiento",
        content:
          "Descubre la emoción de la velocidad con nuestra moto deportiva de última generación. Diseñada para amantes de la adrenalina.",
      },
    };
  },
  created() {
    fetch("https://api.pexels.com/v1/search?query=motorcycle", {
      headers: {
        Authorization:
          "lhXOzdWpnm6SCuLEeQAgjy4hJPO3lmanOBrFqSOvOwMjViBrN9i4te2g",
      },
    })
      .then((response) => response.json())
      .then((data) => {
        this.posts.forEach((post, index) => {
          if (data.photos[index]) {
            post.image = data.photos[index].src.large;
          }
        });
        if (data.photos[2]) {
          this.post3.image = data.photos[5].src.large;
        }
      })
      .catch((error) => console.error(error));
  },
};
</script>

<style scoped>
.main-container {
  background-image: url("..\assets\moto1.png"); /* Reemplaza con la ruta correcta de tu imagen */
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

/* Estilos adicionales para el resto de tu contenido si es necesario */
</style>
