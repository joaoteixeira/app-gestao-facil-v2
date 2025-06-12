<template>
  <div class="row">
    <!-- [ sample-page ] start -->
    <div class="col-sm-12">
      <div class="card">
        <div class="card-header">
          <div class="row">
            <div class="col-sm-10">
              <h3 class="m-0">Servidores</h3>
            </div>
            <div class="col-sm-2 d-grid">

              <RouterLink class="btn btn-primary" to="/servidores/novo">
                <i class="fas fa-plus-circle me-2"></i>Novo
              </RouterLink>

            </div>

          </div>
        </div>
        <div class="card-body p-0">
          <table class="table m-0">
            <thead>
              <tr>
                <th>#</th>
                <th>Id</th>
                <th>Nome</th>
                <th>Siape</th>
                <th>Data Nascimento</th>
                <th>E-mail</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(servidor, index) in servidores" :key="servidor.id">
                <td>{{ index + 1 }}</td>
                <td>{{ servidor.id }}</td>
                <td>{{ servidor.nome }}</td>
                <td>{{ servidor.siape }}</td>
                <td>{{ formatDate(servidor.dataNascimento) }}</td>
                <td>{{ servidor.email }}</td>
              </tr>
            </tbody>
          </table>

        </div>
      </div>
    </div>
    <!-- [ sample-page ] end -->
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import dayjs from 'dayjs';
import axios from 'axios';

export default defineComponent({
  name: 'IndexView',

  data() {
    return {
      servidores: [],
      loading: false
    }
  },

  mounted() {
    this.carregarServidores();
  },

  methods: {
    async carregarServidores() {

      try {
        const response = await axios.get('http://localhost:3000/servidores',
           {
            headers: {
              'Content-Type': 'application/json',
              'ngrok-skip-browser-warning': '69420'
            }
          }
        );

        if(response.status == 200) {
          this.servidores = response.data;
        }


      } catch {}

    },


    formatDate(dateString) {
      const date = dayjs(dateString);
      return date.format('DD/MM/YYYY');
    }
  }
});
</script>
