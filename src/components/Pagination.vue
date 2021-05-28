<template>
  <div>
    <div class="pagination-row">
      <button class="pagination-button">previous</button>
      <span v-for="(item, index) in new Array(10)" :key="index">
        <button class="pagination-button">
          {{ index + 1 }}
        </button>
      </span>
      <button class="pagination-button">next</button>
    </div>
    <slot name="data" :pageNumber="pageNumber" />
  </div>
</template>

<script>
export default {
  name: "Pagination",
  props: ["prduct"],
};
</script>

<style scoped>
.pagination-button {
  padding: 8px;
  margin: 2px;
  border-radius: 3px;
  font-size: 1em;
  cursor: pointer;
}
</style>