<template>
  <div id="app">
    <v-select v-model="selected" v-bind="config" />
    <v-select v-model="selected" v-bind="config">
      <template #sticky-footer>
        <div class="title">Test</div>
        <div class="subtitle">
          Multiline
        </div>
      </template>
      <template #sticky-header>
        <div class="title">Test</div>
        <div class="subtitle">
          Multiline
        </div>
      </template>
    </v-select>
  </div>
</template>

<script>
import vSelect from '../src/components/Select';
import countries from '../docs/.vuepress/data/countryCodes';
import books from '../docs/.vuepress/data/books';

export default {
  components: { vSelect },
  data: () => ({
    selected: null,
    config: {
      options: countries,
    },
  }),
};
</script>

<style>
html,
body {
  margin: 0;
  height: 100%;
  font-family: -apple-system, sans-serif;
}

#app {
  height: 100%;
  margin: 10rem;
}

hr {
  border: none;
  border-bottom: 1px solid #cacaca;
  margin-bottom: 1em;
  padding-top: 1em;
  width: 90%;
}
</style>
