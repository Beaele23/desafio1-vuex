<template>
  <div class="juegos">
    <header class="text-center my-3">
      <h1>Lista de juegos</h1>
    </header>
    <main class="container">
      <section class="lista-productos">
        <table class="table table-borderless">
          <thead class="text-center text-light">
            <tr class="text-light">
              <th scope="col" class="fs-2">Código</th>
              <th scope="col" class="fs-2">Nombre</th>
              <th scope="col" class="fs-2">Stock</th>
              <th scope="col" class="fs-2">Precio</th>
              <th scope="col" class="fs-2">V. Stock</th>
            </tr>
          </thead>
          <tbody class="text-light fs-3">
            <tr v-for="(juego, index) in juegos" :key="index">
              <th scope="row">{{ juego.codigo }}</th>
              <td>{{ juego.nombre }}</td>
              <td>{{ juego.stock }}</td>
              <td>{{ juego.precio }}</td>
              <div class="btn-group">
                <button
                  class="btn btn-dark btn-sm rounded-circle mx-2"
                  @click="agregar(juego.codigo)"
                >
                  <i class="bi bi-plus-circle"></i>
                </button>
                <button
                  class="btn btn-dark btn-sm rounded-circle"
                  @click="disminuir(juego.codigo, juego.stock)"
                >
                  <i class="bi bi-dash-circle"></i>
                </button>
              </div>
              <td></td>
            </tr>
          </tbody>
        </table>
      </section>
    </main>
  </div>
</template>

<script>
import { mapState, mapActions } from "vuex";

export default {
  name: "JuegosView",
  components: {},
  data() {
    return {};
  },
  computed: {
    ...mapState(["juegos"]),
  },

  methods: {
    ...mapActions(["setJuegos", "incrementar", "onDisminuir"]),
    agregar(codigo) {
      this.incrementar(codigo);
    },
    disminuir(codigo, stock) {
      if (stock > 0) {
        this.onDisminuir(codigo);
      }
    },
  },
  created() {
    this.setJuegos();
  },
};
</script>



<style scoped>
h1 {
  font-family: "Chakra Petch", sans-serif;
}
.fs-2 {
  font-family: "Chakra Petch", sans-serif;
}
</style>