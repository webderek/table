<template>
  <tr class="head var" :style="headProperties">
    <th class="head-cell" v-for="item of headData" :key="item">{{ item.charAt(0).toUpperCase() + item.slice(1) }}</th>
  </tr>
</template>

<script>
export default {
  name: 'tableHead',
  props: {
    headData: Array,
     headProperties: Object
  },
}
</script>

<style scoped>

.head-cell {
  padding: 10px 20px;
  background: var(--bg-color);
  color: var(--font-color);
  border-right: 1.5px solid;
  font-size: 15px;
}
</style>
