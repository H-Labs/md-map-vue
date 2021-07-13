<template>
  <textarea
      class="editor"
      v-model="text"
      @input="mdChanged"></textarea>
</template>

<script>
export default {
  name: 'Editor',
  props: {
    md: String,
  },
  data() {
    return {
      text: '',
    };
  },
  watch: {
    md(newValue, oldValue) {
      if (newValue !== oldValue) {
        this.text = newValue;
      }
    },
  },
  mounted() {
    this.text = this.md;
  },
  methods: {
    mdChanged() {
      this.$emit('update', this.text);
    },
  },
};
</script>

<style
    lang="scss"
    scoped>
  .editor {
    flex: 1;
    padding: 8px;
    font-size: 16px;
    line-height: 24px;
    color: #333;
    background-color: #F5F5F5;
    white-space: pre;
    overflow: auto;
    &:focus {
      outline: none;
    }
  }
</style>
