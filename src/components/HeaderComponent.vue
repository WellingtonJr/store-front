<template>
  <header class="p-3 text-bg-dark">
    <div class="container">
      <div
        class="
          d-flex
          flex-wrap
          justify-content-center justify-content-lg-start
          navbar-store
        "
      >
        <router-link to="/"
          ><img
            src="@/assets/img/logo-store.png"
            alt="StoreImage"
            class="logo-store"
        /></router-link>

        <ul
          class="
            nav
            col-12 col-lg-auto
            me-lg-auto
            mb-2
            justify-content-center
            mb-md-0
          "
        >
          <li>
            <router-link to="/"
              ><a href="#" class="nav-link px-2 text-white"
                >Início</a
              ></router-link
            >
          </li>
          <li><a href="#" class="nav-link px-2 text-white">Produtos</a></li>
          <!-- <li><a href="#" class="nav-link px-2 text-white">Pricing</a></li>
          <li><a href="#" class="nav-link px-2 text-white">FAQs</a></li> -->
          <li><a href="#" class="nav-link px-2 text-white">Sobre</a></li>
        </ul>

        <!-- <form class="col-12 col-lg-auto mb-3 mb-lg-0 me-lg-3" role="search">
          <input
            type="search"
            class="form-control form-control-dark text-bg-dark"
            placeholder="Procurar..."
            aria-label="Search"
          />
        </form> -->

        <div class="text-end">
          <router-link to="/login"
            ><button type="button" class="btn btn-outline-light me-2">
              Entrar
            </button></router-link
          >

          <button type="button" class="btn btn-warning">Cadastre-se</button>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
};
</script>

<style>
.logo-store {
  width: 55px;
  border-radius: 50%;
  transform: rotate(-25deg);
}
.navbar-store {
  display: flex;
  align-items: center;
}
</style>