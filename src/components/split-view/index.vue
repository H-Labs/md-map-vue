<template>
  <div class="split-view">
    <div class="left">
      <editor
          :md="md"
          @update="mdUpdated($event)"></editor>
    </div>
    <div class="right">
      <chart
          :md="md"></chart>
    </div>
  </div>
</template>

<script>
import Editor from '@/components/editor/index.vue';
import Chart from '@/components/chart/index.vue';

export default {
  name: 'SplitView',
  components: {
    Editor,
    Chart,
  },
  data() {
    return {
      md: `# Markdown to mindmap

## supports heading 1~3

## and list

+ A
+ B
+ C`,
    };
  },
  methods: {
    mdUpdated(content) {
      this.md = content;
    },
  },
};
</script>

<style
    lang="scss"
    scoped>
  .split-view {
    display: flex;
    height: 100%;

    .left,
    .right {
      display: flex;
      flex-direction: column;
      flex: 1;
      height: 100%;
    }

    .left {
      border-right: solid 2px #EEE;
    }
  }
</style>
