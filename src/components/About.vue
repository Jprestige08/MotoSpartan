<template>
  <div class="container">
    <div class="card bg-dark text-white p-4">
      <h1 class="my-4">SOBRE NOSOTROS </h1>
      <p>
        <strong>¡Bienvenido a Motospartan: Donde la Pasión por las Motos y la Aventura se Fusionan en Miami!</strong>
      </p>
      <p>
        En Motospartan, no estamos simplemente en el negocio de las motos; estamos en la búsqueda inquebrantable de la pasión,
        la libertad y la emoción que solo las dos ruedas pueden ofrecer. Nosotros no solo vendemos motos; entregamos sueños,
        impulsamos emociones y cultivamos una comunidad de intrépidos aventureros.
      </p>
      <p>
        Somos más que una tienda; somos un equipo de apasionados motociclistas dedicados a convertir cada viaje en una
        experiencia inolvidable. Desde las callejeras más elegantes hasta las todoterreno más intrépidas, cada moto que
        vendemos en Motospartan es una puerta de entrada a un mundo de posibilidades.
      </p>
      <!-- Carrusel de Imágenes -->
      <div id="imageCarousel" class="carousel slide mb-4" data-bs-ride="carousel">
        <div class="carousel-inner">
          <div v-for="(image, index) in storeImages" :key="index" :class="{ 'carousel-item': true, active: index === 0 }">
            <img :src="image" class="d-block w-100" alt="Imagen de la tienda">
          </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#imageCarousel" data-bs-slide="prev">
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Anterior</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#imageCarousel" data-bs-slide="next">
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Siguiente</span>
        </button>
      </div>

      <h2>Ubicación: Miami, FL</h2>
      <p>
        Encuéntranos en el corazón de la emocionante ciudad de Miami. Nuestra ubicación está diseñada para ser más que una
        tienda; es un punto de encuentro para todos los amantes de las motos en la región.
      </p>

      <h2>Horarios de Apertura:</h2>
      <p>
        Estamos aquí para ti todos los días de la semana. Abiertos de lunes a domingo, estamos listos para satisfacer tus
        necesidades de motocicletas y compartir la pasión, sin importar el día.
      </p>

      <h2>Lo que nos distingue:</h2>
      <ul>
        <li><strong>Pasión Desbordante:</strong> Nosotros entendemos las miradas apasionadas, las aceleraciones llenas de
          adrenalina y el ronroneo tranquilizador del motor. Compartimos tu amor por las motos porque vivimos y respiramos
          la cultura motociclista.</li>

        <li><strong>Asesoramiento Personalizado:</strong> No solo vendemos motos; ayudamos a encontrar tu moto perfecta.
          Nuestro equipo está aquí para guiarte, aconsejarte y asegurarse de que cada compra sea una decisión emocionante y
          bien informada.</li>

        <li><strong>Comunidad Vibrante:</strong> En Motospartan, no eres solo un cliente, eres parte de una familia de
          amantes de las motos. Organizamos eventos, rutas y actividades que te conectan con una comunidad que comparte tu
          pasión.</li>

        <li><strong>Compromiso con la Excelencia:</strong> Desde el showroom hasta el taller de servicio, nuestra dedicación
          a la excelencia está en cada detalle. Mantenemos tus sueños en movimiento con servicios de mantenimiento de alta
          calidad y una selección de accesorios de primera.</li>
      </ul>

      <p>
        En Motospartan, estamos aquí para impulsar tu historia de moto, para agregar capítulos de emoción, libertad y pura
        adrenalina. Únete a nosotros en este viaje y descubre la verdadera esencia de la vida sobre dos ruedas. ¡Bienvenido a
        la familia Motospartan en Miami!
      </p>

      <!-- Agregar el mapa de Google sin usar API -->
      <div class="google-map">
        <iframe
          width="100%"
          height="400"
          frameborder="0"
          style="border:0"
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d114964.54559553922!2d-80.31203256630099!3d25.782384195490778!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x88d9b0a20ec8c111%3A0xff96f271ddad4f65!2sMiami%2C%20Florida%2C%20EE.%20UU.!5e0!3m2!1ses-419!2sco!4v1700821072647!5m2!1ses-419!2sco"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      storeImages: [
        'https://scontent-bog1-1.xx.fbcdn.net/v/t39.30808-6/398991286_321023110672672_4398597166349825354_n.jpg?_nc_cat=102&ccb=1-7&_nc_sid=5f2048&_nc_ohc=Fdh76l2JdqoAX84lscB&_nc_ht=scontent-bog1-1.xx&oh=00_AfCUg5UIhTOQE6NUeg-84xRgsgAWpHJ1EFKJx4d4AkhFvQ&oe=6564B872',
        'https://scontent-bog1-1.xx.fbcdn.net/v/t39.30808-6/398999203_321023120672671_2561480001779328603_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=5f2048&_nc_ohc=WLXNjPQ-NHsAX-jvE1t&_nc_ht=scontent-bog1-1.xx&oh=00_AfAy5-Mh3T2NyXuw5jAInt0_QA3qz8a8AAjVydFW6crJHQ&oe=6565F3A8',
        'https://scontent-bog1-1.xx.fbcdn.net/v/t39.30808-6/398999343_321023117339338_4331544727814764778_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=5f2048&_nc_ohc=JQ3cUPvKXVIAX87lhq0&_nc_ht=scontent-bog1-1.xx&oh=00_AfBqMp9K6lmio1UQT0ubkNR9B2WjxxLAV_EwNGJYmR3MJA&oe=6564D8D1',
      ],
    };
  },
};
</script>

<style>
/* Estilos existentes... */
</style>
