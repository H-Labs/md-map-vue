<template>
  <div
      class="chart">chart</div>
</template>

<script>
// eslint-disable-next-line
import mdMap from 'md-map';

export default {
  name: 'Chart',
  props: {
    md: String,
  },
  watch: {
    md(newValue, oldValue) {
      if (newValue !== oldValue) {
        console.log(mdMap.parse(newValue));
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
