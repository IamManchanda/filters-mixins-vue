<template>
  <div>
    <input type="text" v-model="filterText">
    <ul>
      <li v-for="fruit in filteredFruits">
        {{ fruit }}
      </li>
    </ul>
  </div>
</template>

<script>
import { fruitMixin } from '../fruitMixin.js';

export default {
  mixins: [fruitMixin],
  created() {
    console.log('Inside List Created Hook');
  }
}
</script>

<style lang="scss">
</style>
