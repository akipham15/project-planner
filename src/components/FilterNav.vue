<template>
  <div class="filter-nav">
    <button @click="updateFilter('all')" :class="{active: filter==='all'}">All</button>
    <button @click="updateFilter('complete')" :class="{active: filter==='complete'}">Complete</button>
    <button @click="updateFilter('ongoing')" :class="{active: filter==='ongoing'}">Ongoing</button>
  </div>
</template>

<script>
export default {
  props: ['filter'],
  methods: {
    updateFilter(by) {
      this.$emit("filterChange", by);
    },
  },
};
</script>

<style>
.filter-nav button {
  background: none;
  border: none;
  color: #bbb;
  font-weight: bold;
  outline: none;
  font-size: 12px;
  margin-right: 10px;
  letter-spacing: 1px;
  text-transform: uppercase;
  cursor: pointer;
}
.filter-nav button.active {
    color: #555;
}
</style>