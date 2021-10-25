<template>
  <div>
    <TableHead :headData="headData" :headProperties= "headProperties"> 
    </TableHead>
  </div>
</template>

<script>
import TableHead from './tableHead.vue'
export default {
  name: 'tableHead',
  components: {
    TableHead
  },
  props: {
    headData: Array,
    headProperties: Object,
  },
}
</script>

<style scoped>

</style>
