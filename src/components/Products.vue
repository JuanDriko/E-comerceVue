<template>
    <h1 class="text-center">Nuestros Productos</h1>
  <div class="container d-flex justify-content-between flex-wrap">
    <div v-for="item in data" :key="item.id" class="m-3">
      <div class="card p-2" style="width: 18rem">
        <img :src="item.image" class="card-img-top" alt="Product Image" style="width: 90%;"/>
        <div class="card-body">
          <h5 class="card-title">{{ item.title }}</h5>
          <h5 class="card-title">$ {{item.price}}</h5>
          <p class="card-text">{{ truncatedDescription(item.description) }}</p>     
          <button @click="showFullDescription(item.id)" v-if="!item.showFullDescription" class="btn btn-link">Mostrar más</button>
        <span v-if="item.showFullDescription">{{ item.description }}</span>    
          <a href="#" class="btn btn-primary">Ver Producto</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: [],
    };
  },
  methods: {
    getData() {
      fetch("https://fakestoreapi.com/products/")
        .then((response) => response.json())
        .then((data) => {
          console.log("productos:", data);
          this.data = data;
        });
    },
    truncatedDescription(description) {
      return description.slice(0, 100) + '...';
    },
    showFullDescription(itemId) {
      const item = this.data.find(item => item.id === itemId);
      if (item) {
        item.showFullDescription = true;
      }
    }
  },
  mounted() {
    this.getData();
  },
};
</script>

<style scoped></style>
