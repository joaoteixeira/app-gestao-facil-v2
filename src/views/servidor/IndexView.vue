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

              <button type="button" class="btn btn-primary">
                <i class="fas fa-plus-circle me-2"></i>Novo
              </button>

            </div>

          </div>
        </div>
        <div class="card-body p-0">

          <table class="table m-0">
            <thead>
              <tr>
                <th>#</th>
                <th>Nome</th>
                <th>Siape</th>
                <th>Data Nascimento</th>
                <th>E-mail</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>1</td>
                <td>João Silva</td>
                <td>1234567</td>
                <td>15/03/1980</td>
                <td>joao.silva@email.com</td>
              </tr>
              <tr>
                <td>2</td>
                <td>Maria Santos</td>
                <td>7654321</td>
                <td>22/07/1985</td>
                <td>maria.santos@email.com</td>
              </tr>
              <tr>
                <td>3</td>
                <td>Pedro Oliveira</td>
                <td>9876543</td>
                <td>10/11/1978</td>
                <td>pedro.oliveira@email.com</td>
              </tr>
              <tr>
                <td>4</td>
                <td>Ana Costa</td>
                <td>4567890</td>
                <td>05/05/1990</td>
                <td>ana.costa@email.com</td>
              </tr>
              <tr>
                <td>5</td>
                <td>Carlos Souza</td>
                <td>2345678</td>
                <td>18/09/1982</td>
                <td>carlos.souza@email.com</td>
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

export default defineComponent({
  name: 'IndexView',
  data() {
    return {
      servidores: [],
      loading: false
    }
  },
  methods: {

  }
});
</script>