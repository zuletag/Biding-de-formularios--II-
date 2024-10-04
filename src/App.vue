<script>
export default {
  name: "App",
  data() {
    return {
      usuario: {
        titulo: "",
        emoji: "",
        apreciacion: "",
        competencias: [],
        opinion: "",
      },
    };
  },
};
</script>

<template>
  <div class="container-fluid">
    <div class="row m-5">
      <!-- Columna izquierda -->
      <div class="col-12 col-lg-6 bg-dark text-light p-5 rounded-4 my-2">
        <form>
          <!-- Título -->
          <div class="d-flex align-items-center">
            <div class="me-3">
              <label for="titulo" class="form-label">Título:</label>
            </div>
            <div class="flex">
              <input v-model="usuario.titulo" id="titulo" type="text" class="form-control"
                placeholder="Escribe tu título">
            </div>
          </div>
          <hr class="my-4">
          <!-- Emoji -->
          <div class="d-flex align-items-center">
            <div class="me-3">
              <label for="emoji" class="form-label">Emoji:</label>
            </div>
            <div class="flex">
              <select v-model="usuario.emoji" id="emoji" class="form-select">
                <option>👨‍💻</option>
                <option>👩‍💻</option>
                <option>🦤</option>
                <option>🐒</option>
                <option>🤖</option>
                <option>🐴</option>
              </select>
            </div>
          </div>
          <hr class="my-4">
          <!-- Apreciación -->
          <div class="d-flex align-items-center">
            <div class="me-2">
              <label class="form-label">Apreciación:</label>
            </div>
            <div class="d-flex justify-content-between">
              <label class="form-check-label"><input type="radio" value="Regular" v-model="usuario.apreciacion"
                  class="form-check-input ms-3"> Regular</label>
              <label class="form-check-label"><input type="radio" value="Bien" v-model="usuario.apreciacion"
                  class="form-check-input ms-3"> Bien</label>
              <label class="form-check-label"><input type="radio" value="Muy bien" v-model="usuario.apreciacion"
                  class="form-check-input ms-3"> Muy bien</label>
              <label class="form-check-label"><input type="radio" value="Increíble" v-model="usuario.apreciacion"
                  class="form-check-input ms-3"> Increíble</label>
            </div>
          </div>
          <hr class="my-4">
          <!-- Competencias -->
          <div class="d-flex align-items-center">
            <div class="me-3">
              <label class="form-label">Competencias aprendidas:</label>
            </div>
            <div class="d-flex justify-content-around flex-wrap">
              <div class="col-6">
                <div class="form-check me-3">
                  <input type="checkbox" v-model="usuario.competencias" value="Morfología de un componente"
                    class="form-check-input">
                  <label class="form-check-label">Morfología de un componente</label>
                </div>
                <div class="form-check me-3">
                  <input type="checkbox" v-model="usuario.competencias" value="One-Way y Two-Way data binding"
                    class="form-check-input">
                  <label class="form-check-label">One-Way y Two-Way data binding</label>
                </div>
                <div class="form-check">
                  <input type="checkbox" v-model="usuario.competencias" value="El patrón de diseño MVVM"
                    class="form-check-input">
                  <label class="form-check-label">El patrón de diseño MVVM</label>
                </div>
              </div>
              <div class="col-6">
                <div class="form-check me-3">
                  <input type="checkbox" v-model="usuario.competencias" value="Directivas" class="form-check-input">
                  <label class="form-check-label">Directivas</label>
                </div>
                <div class="form-check me-3">
                  <input type="checkbox" v-model="usuario.competencias" value="Estado" class="form-check-input">
                  <label class="form-check-label">Estado</label>
                </div>
              </div>
            </div>
          </div>
          <hr class="my-4">
          <!-- Opinión -->
          <div class="d-flex align-items-center">
            <div class="me-3">
              <label for="opinion" class="form-label">Opinión:</label>
            </div>
            <textarea v-model="usuario.opinion" id="opinion" class="form-control"
              placeholder="Escribe tu opinión"></textarea>
          </div>
        </form>
      </div>

      <!-- Columna derecha (solo para ver la data) -->
      <div class="col-12 col-lg-6 my-2">
        <div class="respuestas p-5 rounded-4">
          <div class="text-wrap text-break">
            <h1>{{ usuario.emoji }}</h1>
            <h1>{{ usuario.titulo }}</h1>
            <p class="fs-3">Y me parece {{ usuario.apreciacion }}</p>
            <p class="fs-5">He aprendido:</p>
            <p class="fs-5 fw-lighter"> "{{ usuario.competencias.join(", ") }}"</p>
            <p class="fs-5">Mi opinion hasta ahora del framework es:</p>
            <p class="fs-5 fw-lighter"> {{ usuario.opinion }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<style scoped>
.bg-dark {
  background-color: #000 !important;
}

.form-label {
  padding: 0%;
  margin: 0%;
}


.form-label {
  font-weight: bold;
}

.respuestas {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  border: 1px solid #ccc;
  height: 100%;
}
</style>
