<template>
  <!-- <div class="row py-5 b-light"> -->
  <div class="col px-5">
    <div class="card shadow-sm">
      <img src="" alt="teste" width="100%" height="225" />

      <div class="card-body">
        <p class="card-text">asadadsasdads</p>
        <div class="d-flex justify-content-between align-items-center">
          <div class="btn-group">
            <button type="button" class="btn btn-sm btn-outline-secondary">
              asdasd
            </button>
            <button type="button" class="btn btn-sm btn-outline-secondary">
              asdasdas
            </button>
          </div>
          <small class="text-muted">asdad</small>
        </div>
      </div>
    </div>
  </div>
  <!-- </div> -->
</template>

<script>
export default {
  name: "ProdutoComponent",
  data() {
    return {};
  },
  methods: {
    //todo
    createProduto(produto) {
      console.log(produto);
    },
  },
  mounted() {
    this.$root.$on("createProduto", this.createProduto);
  },
};
</script>

<style>
</style>