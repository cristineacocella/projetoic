<template>
  <div id="container-header">
    <header class="header">
      <div class="header-div">
        <img
          src="https://static.wixstatic.com/media/b91e09_95ec298e6ed645d197af640983985c6c~mv2.png/v1/fill/w_468,h_112,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/logo_ic_v5_20210604_a4_logo_hQ.png"
          alt="Logo Intuitive Care"
        />
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: "HeaderHeader",
  props: {
    msg: String,
  },
};
</script>

<style scoped>
.header-div {
  display: flex;
  justify-content: center;
  padding: 2rem 0;
  box-shadow: 0rem 0.5rem 0.5rem #cccccc;
}

.header-div img {
  width: 15%;
}
</style>
