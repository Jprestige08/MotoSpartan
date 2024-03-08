<template>
  <div class="container about-section">
    <h1 class="my-4">CONOCE TU MOTO</h1>
    <div class="row">
      <div class="col-md-6">
        <div class="card bg-dark text-white p-4">
          <form @submit.prevent="getMotorcycles">
            <div class="form-group">
              <label for="make">Marca de la moto:</label>
              <input
                type="text"
                class="form-control"
                v-model="make"
                id="make"
              />
            </div>
            <div class="form-group">
              <label for="model">Modelo de la moto:</label>
              <input
                type="text"
                class="form-control"
                v-model="model"
                id="model"
              />
            </div>
            <div class="form-group">
              <label for="year">Año de la moto:</label>
              <input
                type="number"
                class="form-control"
                v-model="year"
                id="year"
              />
            </div>
            <button type="submit" class="btn btn-primary">Buscar Motos</button>
          </form>
        </div>
      </div>
      <div class="col-md-6">
        <div v-if="motorcycleDetails && motorcycleDetails.length">
          <div class="card bg-dark mt-3">
            <div class="card-body">
              <h2 class="title text-white">
                {{ motorcycleDetails[currentIndex].make }}
                {{ motorcycleDetails[currentIndex].model }}
              </h2>
              <table class="table text-white">
                <tbody>
                  <tr>
                    <th scope="row">Año</th>
                    <td>{{ motorcycleDetails[currentIndex].year }}</td>
                  </tr>
                  <tr>
                    <th scope="row">Tipo</th>
                    <td>{{ motorcycleDetails[currentIndex].type }}</td>
                  </tr>
                  <tr>
                    <th scope="row">Desplazamiento</th>
                    <td>{{ motorcycleDetails[currentIndex].displacement }}</td>
                  </tr>
                  <tr>
                    <th scope="row">Motor</th>
                    <td>{{ motorcycleDetails[currentIndex].engine }}</td>
                  </tr>
                  <tr>
                    <th scope="row">Potencia</th>
                    <td>{{ motorcycleDetails[currentIndex].power }}</td>
                  </tr>
                  <tr>
                    <th scope="row">Torque</th>
                    <td>{{ motorcycleDetails[currentIndex].torque }}</td>
                  </tr>
                  <tr>
                    <th scope="row">Compresión</th>
                    <td>{{ motorcycleDetails[currentIndex].compression }}</td>
                  </tr>
                  <tr>
                    <th scope="row">Sistema de combustible</th>
                    <td>{{ motorcycleDetails[currentIndex].fuel_system }}</td>
                  </tr>
                  <tr>
                    <th scope="row">Peso total</th>
                    <td>{{ motorcycleDetails[currentIndex].total_weight }}</td>
                  </tr>
                  <button
                    @click="showPrevious"
                    :disabled="currentIndex === 0"
                    class="btn btn-primary"
                  >
                    Anterior
                  </button>
                  <button
                    @click="showNext"
                    :disabled="currentIndex === motorcycleDetails.length - 1"
                    class="btn btn-primary"
                  >
                    Siguiente
                  </button>
                </tbody>
              </table>
            </div>
          </div>
        </div>
        <div v-else>
          <div class="card bg-dark mt-3">
            <div class="card-body">
              <p class="text-white">
                No hay detalles de motocicleta disponibles.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "About",
  data() {
    return {
      make: "",
      model: "",
      year: "",
      motorcycleDetails: null,
      currentIndex: 0,
    };
  },
  methods: {
    async getMotorcycles() {
      console.log("Formulario enviado");

      try {
        const response = await axios.get(
          "https://motorcycles-by-api-ninjas.p.rapidapi.com/v1/motorcycles",
          {
            params: {
              make: this.make,
              model: this.model,
              year: this.year,
            },
            headers: {
              "X-RapidAPI-Key":
                "3adab158demsh3688f101613648fp191f99jsnc5ce03daa1ab",
              "X-RapidAPI-Host": "motorcycles-by-api-ninjas.p.rapidapi.com",
            },
          }
        );

        console.log(response.data);

        this.motorcycleDetails = response.data;
        this.currentIndex = 0;

        if (!this.motorcycleDetails || this.motorcycleDetails.length === 0) {
          console.log("No se encontraron detalles de motocicletas.");
        }
      } catch (error) {
        console.error("Error al obtener detalles de la motocicleta:", error);

        if (error.response) {
          console.error("Datos de respuesta:", error.response.data);
          console.error("Estado de respuesta:", error.response.status);
        } else if (error.request) {
          console.error("No se recibió respuesta:", error.request);
        } else {
          console.error("Error al configurar la solicitud:", error.message);
        }
      }
    },

    showNext() {
      if (this.currentIndex < this.motorcycleDetails.length - 1) {
        this.currentIndex += 1;
      }
    },

    showPrevious() {
      if (this.currentIndex > 0) {
        this.currentIndex -= 1;
      }
    },
  },
};
</script>

<style>
.about-section {
  background-image: url("../assets/interior1.png");
  background-size: cover;
  background-position: center center;
  padding: 170px;
  color: white;
}

.title,
.details li,
.card-body p {
  color: white;
  /* Otros estilos necesarios */
}
</style>
