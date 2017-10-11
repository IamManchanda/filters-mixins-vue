<template>
  <div class="grid-container margin-top-2">
    <div class="grid-x grid-margin-x">
      <div class="cell medium-8 medium-offset-2">
        <h2>Filters &amp; Mixins</h2>
        <p> {{ text | to-upper-case | to-lower-case }} </p>
        <button class="button primary" @click="fruits.push('Berries')">Add new Item</button>
        <input type="text" v-model="filterText">
        <ul>
          <li v-for="fruit in filteredFruits">
            {{ fruit }}
          </li>
        </ul>
        <hr>
        <app-list></app-list> 
      </div>
    </div>
  </div>
</template>

<script>
import AppList from './components/AppList.vue';
import { fruitMixin } from './fruitMixin.js';

export default {
  mixins: [fruitMixin],
  data() {
    return {
      text: 'Hello There',
    };
  },
  filters: {
    toUpperCase(value) {
      return value.toUpperCase();
    } 
  },
  components: { AppList }
}
</script>

<style lang="scss">
</style>
