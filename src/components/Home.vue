<template>
  <div>
    <h1>{{ msg }}</h1>
    <div class="container">
      <pagination />
      <div class="row mb-5">
        <div
          class="col-md-4 mt-4"
          v-for="product in products"
          :key="product.id"
        >
          <Card :prduct="product" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./Card.vue";
import axios from "axios";
import Pagination from "./Pagination.vue";

export default {
  name: "Home",
  components: {
    Card,
    Pagination,
  },
  props: {
    msg: String,
  },
  data() {
    return {
      products: [],
      pageNumber: 2,
    };
  },
  methods: {
    setProduct(data) {
      this.products = data;
    },
  },
  mounted() {
    axios
      .get(`https://picsum.photos/v2/list?page=${this.pageNumber}&limit=100`)
      .then((response) => {
        this.setProduct(response.data);
        console.log(response.data);
      })
      .catch((error) => {
        throw error;
      });
  },
};
</script>


