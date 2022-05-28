<template>
  <div id="vue-root">
    <ag-grid-vue
      style="height: 500px"
      :columnDefs="columnDefs.value"
      :rowData="rowData.value"
      :defaultColDef="defaultColDef"
      rowSelection="multiple"
      animateRows="true"
      @cell-clicked="cellWasClicked"
      @grid-ready="onGridReady"
    >
    </ag-grid-vue>
  </div>
</template>

<script>
import "ag-grid-community/dist/styles/ag-grid.css";
import "ag-grid-community/dist/styles/ag-theme-alpine.css";
import { AgGridVue } from "ag-grid-vue3";
import { reactive, onMounted, ref } from "vue";
// import { useFile } from "@vue-reactivity/fs";

export default {
  name: "App",
  components: {
    AgGridVue,
  },

  setup() {
    const gridApi = ref(null);

    const onGridReady = (params) => {
      gridApi.value = params.api;
    };

    let rowData = reactive({});

    const columnDefs = reactive({
      value: [{ field: "make" }, { field: "model" }, { field: "price" }],
    });

    const defaultColDef = {
      sortable: true,
      filter: true,
    };

    // const csvJSON = (csv) => {
    //   const lines = csv.split("\n");
    //   console.log(lines);
    //   const result = [];
    //   const headers = lines[0].split(";");
    //   console.log(headers);
    //   for (let i = 1; i < lines.length; i++) {
    //     if (!lines[i]) continue;
    //     const obj = {};
    //     const currentline = lines[i].split(";");

    //     for (let j = 0; j < headers.length; j++) {
    //       obj[headers[j]] = currentline[j];
    //     }
    //     result.push(obj);
    //   }

    //   return result;
    // };

    // const fs = require("fs");
    // const csv = require("fast-csv");

    // const stream = fs.createReadStream("../assets/Relatorio_cadop.csv");

    // const csv = useFile("../assets/Relatorio_cadop.csv");
    // const csvJason = csvJSON(csv);

    onMounted(() => {
      fetch("https://www.ag-grid.com/example-assets/row-data.json")
        .then((result) => result.json())
        .then((remoteRowData) => (rowData.value = remoteRowData));
    });

    return {
      onGridReady,
      columnDefs,
      rowData,
      defaultColDef,
      cellWasClicked: (event) => {
        // Example of consuming Grid Event
        console.log("cell was clicked", event);
      },
    };
  },
};
</script>

<style scoped></style>

// style="width: 500px; height: 200px" // class="ag-theme-alpine" //
:columnDefs="columnDefs" // :rowData="rowData"
