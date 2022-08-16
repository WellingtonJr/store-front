<template>
  <div class="">
    <div class="row">
      <h2 class="text-right py-3 px-5">Produtos</h2>
    </div>

    <div class="container wrap">
      <div
        class="col px-5 py-2 item"
        v-for="(produto, index) in produtos"
        :key="index"
      >
        <div class="card shadow-sm">
          <img :src="fotos[index]" alt="teste" width="100%" height="225" />

          <div class="card-body">
            <p class="card-text">
              {{ produto.price | currency("R$", 2, { decimalSeparator: "," }) }}
            </p>
            <div class="d-flex justify-content-between align-items-center">
              <div class="btn-group">
                <button type="button" class="btn btn-sm btn-outline-secondary">
                  add
                </button>
                <button type="button" class="btn btn-sm btn-outline-secondary">
                  more
                </button>
              </div>
              <small class="text-muted">wstore</small>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import ProducoComponent from "../components/ProdutoComponent.vue";
import axios from "axios";

export default {
  name: "ProdutosView",
  components: {
    // ProducoComponent,
  },
  data() {
    return {
      //todo
      produtos: [],
      fotos: [],
    };
  },
  methods: {
    async getProdutos() {
      let produtos = await axios
        .get("https://62df2213976ae7460be831a4.mockapi.io/bookstore")
        .then((resp) => resp.data);
      console.log(produtos);

      produtos.forEach((element, index) => {
        let photoUrl = `https://picsum.photos/id/${index}/200/300`;
        this.fotos.push(photoUrl);
        this.produtos.push(element);
      });
    },
  },
  created() {
    //todo
  },
  mounted() {
    //todo
    this.getProdutos();
  },
};
</script>

<style scoped>
.container {
  display: flex;
  height: 100vh;
}
.wrap {
  flex-wrap: wrap;
}
.item {
  max-width: 300px;
  max-height: 400px;
}
.card {
  box-shadow: 10px 10px 5px rgb(11, 13, 14);
}
h2 {
  font-weight: 500;
  text-align: left;
  text-shadow: 1px 1px 2px #000000;
}
</style>