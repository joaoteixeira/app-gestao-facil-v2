<template>
  <div class="row">
    <div class="col-sm-12">
      <div class="card">
        <div class="card-header">
          <div class="row">
            <div class="col-sm-10">
              <h3 class="m-0">Novo Servidor</h3>
            </div>
            <div class="col-sm-2 d-grid">
              <RouterLink class="btn btn-secondary" to="/servidores">
                <i class="fas fa-arrow-left me-2"></i>Voltar
              </RouterLink>
            </div>
          </div>
        </div>
        <div class="card-body">
          <form @submit.prevent="salvar">
            <div class="row">
              <div class="col-sm-6 mb-3">
                <label for="nome" class="form-label">Nome</label>
                <input type="text" class="form-control" id="nome" v-model="formDados.nome">
              </div>
              <div class="col-sm-6 mb-3">
                <label for="siape" class="form-label">Siape</label>
                <input type="text" class="form-control" id="siape" v-model="formDados.siape">
              </div>
            </div>

            <div class="row">
              <div class="col-sm-6 mb-3">
                <label for="dataNascimento" class="form-label">Data de Nascimento</label>
                <input type="date" class="form-control" id="dataNascimento" v-model="formDados.dataNascimento">
              </div>
              <div class="col-sm-6 mb-3">
                <label for="email" class="form-label">E-mail</label>
                <input type="email" class="form-control" id="email" v-model="formDados.email">
              </div>
            </div>

            <div class="row">
              <div class="col-sm-12">
                <button type="submit" class="btn btn-primary">
                  <i class="fas fa-save me-2"></i>Salvar
                </button>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'FormView',

  data() {
    return {
      formDados: {
        nome: '',
        siape: '',
        dataNascimento: '',
        email: ''
      }
    }
  },

  methods: {
    salvar() {
      console.log('DADOS DO FORMULARIO', this.formDados)
    }
  }

});
</script>
