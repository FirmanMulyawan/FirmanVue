<template>
  <div class="card shadow card-product">
    <img :src="prduct.download_url" class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">{{ prduct.author }}</h5>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["prduct"],
};
</script>

<style>
</style>