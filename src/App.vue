<template>
  <div id="app">
    <header-component></header-component>
    <main id="main"><router-view /></main>

    <footer-component></footer-component>
  </div>
</template>

<script>
import HeaderComponent from "@/components/HeaderComponent.vue";
import FooterComponent from "@/components/FooterComponent.vue";

export default {
  components: {
    HeaderComponent,
    FooterComponent,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(0, 0, 0);
  display: flex;
  min-height: 100vh;
  flex-direction: column;
}

#main {
  flex: 1;
}

body {
  background-color: rgb(255, 255, 255);
  color: rgb(0, 0, 0);
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: aliceblue;
}

nav a.router-link-exact-active {
  color: aliceblue;
}

a {
  text-decoration: none;
}
</style>
