<template>
  <div class="div-container">
    <div class="div-box">
      <div class="div-grid">
        <div class="title">
          <p>Relação de Operadoras Ativas ANS</p>
        </div>
        <div class="search-box">
          <input type="search" name="search" class="search" />
        </div>
        <div class="table">
          <vue-csv-input name="Relatorio_cadop"> </vue-csv-input>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BoxBox",
  props: {
    msg: String,
  },
};
</script>

<style scoped>
.div-container {
  margin-top: 0.5rem;
  background-color: #f2f2f2;
}

.div-box {
  display: inline-block;
  background-color: white;
  margin: 2rem 0;
  width: 98%;
}

.div-grid {
  padding: 2rem;
  display: grid;
  grid-template-columns: 1fr 2fr;
  row-gap: 2rem;
  align-content: space-between;
}

.search-box {
  justify-self: flex-end;
  width: 50%;
}
.search {
  display: inline-block;
  width: 100%;
}

.title {
  justify-self: flex-start;
  color: #4d4dff;
}

.title p {
  font-size: 1.6rem;
}

.table {
  grid-column: 1 / -1;
  border: 0.1rem solid black;
  height: 25rem;
}
</style>
