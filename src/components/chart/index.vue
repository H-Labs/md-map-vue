<template>
  <div
      class="chart">chart</div>
</template>

<script>
export default {
  name: 'Chart',
  props: {
    md: String,
  },
  watch: {
    md(newValue, oldValue) {
      if (newValue !== oldValue) {
        // update
      }
    },
  },
};
</script>

<style
    lang="scss"
    scoped>
  .chart {
    flex: 1;
    padding: 8px;
  }
</style>
