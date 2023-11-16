<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">ShopStore</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNavDropdown"
        aria-controls="navbarNavDropdown"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavDropdown">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Inicio</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#"></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Nosotros</a>
          </li>
          <li class="nav-item dropdown">
            <a
              class="nav-link dropdown-toggle"
              href="#"
              role="button"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              Categorías
            </a>
            <ul class="dropdown-menu">
              <li><a class="dropdown-item" href="#">Ropa Hombre</a></li>
              <li><a class="dropdown-item" href="#">Ropa Mujer</a></li>
              <li><a class="dropdown-item" href="#">Electronica</a></li>
            </ul>
          </li>
        </ul>
        <div class="d-flex justify-content-end container-fluid">
          <div class="search-product">
            <input type="text" id="search" placeholder="Busca tu Producto" />
            <button id="search-btn" type="button" class="btn btn-dark m-2">
              Buscar
            </button>
          </div>
          <button id="btn-cart" class="btn btn-outline-dark m-2" type="button">
            <i class="bi-cart-fill me-1"></i>
            Cart
            <span
              id="cart-counter"
              class="badge bg-dark text-white rounded-pill"
              >0</span
            >
          </button>
        </div>
      </div>
    </div>
  </nav>
  <Home/>
  <Products/>
</template>

<script>
import Home from "./components/Home.vue"
import Products from "./components/Products.vue"
export default {
  components:{
    Home,
    Products
  }
};
</script>

<style scoped>
</style>