<template>
  <div id="app">
    <v-select v-model="selected" v-bind="config" />
    <v-select v-model="selected" v-bind="config">
      <template #sticky-footer>
        <b-row align-v="center">
          <b-col cols="12" md="7">
            <slot name="footer-template">
              <div class="title">Can't find your practice?</div>
              <div class="subtitle">
                If you can't find a practice in the list you can add it manually
              </div>
            </slot>
          </b-col>
          <b-col cols="12" md="5" class="text-right">
            <BaseButton
              class="font-weight-bold ml-auto"
              :icon="['fas', 'plus']"
              :variant="variant"
              @click="$emit('add')"
            >
              <div style="font-size: 18px" class="m-0">
                <slot name="footer-button">Add Manually</slot>
              </div>
            </BaseButton>
          </b-col>
        </b-row>
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
