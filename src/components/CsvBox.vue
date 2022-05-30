<template>
  <ag-grid-vue
    style="width: 100%; height: 50%"
    class="ag-theme-alpine"
    :columnDefs="columnDefs"
    :rowData="rowData"
  >
  </ag-grid-vue>
</template>

<script>
import "ag-grid-community/dist/styles/ag-grid.css";
import "ag-grid-community/dist/styles/ag-theme-alpine.css";
import { AgGridVue } from "ag-grid-vue3";
import Json from "../assets/csvjson.json";

export default {
  components: {
    AgGridVue,
  },

  data() {
    return {
      json: Json,
      columnDefs: [],
      rowData: [],
    };
  },

  mounted() {
    // esta executando a função de criação das colunas e das linhas
    this.colunas();
    this.conteudo();
  },

  methods: {
    colunas() {
      let chaves = [];
      let nomeColuna = new Object();
      // pega a quantidade de chaves que o objeto tem e joga na lista chaves
      for (let x in this.json[0]) {
        chaves.push(x);
      }

      //cria um objeto e da pra ele o cabeçalho e o nome dos campo de acordo com a lista de chaves
      for (let i = 0; i <= chaves.length; i++) {
        nomeColuna = {};
        nomeColuna.headerName = chaves[i];
        nomeColuna.field = chaves[i];
        this.columnDefs.push(nomeColuna);
      }
    },

    conteudo() {
      const data = JSON.stringify(Json);
      const format = JSON.parse(data);

      for (let i = 0; i <= format.length - 1; i++) {
        this.rowData.push(format[0]);
      }
    },
  },
};
</script>

<style scoped></style>
