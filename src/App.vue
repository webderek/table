<template>
  <CustomTable :headData="headData" :headProperties="headProperties"/>
</template>

<script>
import { reactive } from '@vue/reactivity'
import CustomTable from './components/customTable.vue'

export default {
  name: 'App',
  components: {
    CustomTable
  },
  setup() {
    const tableData = reactive(
      { id: "0", name: "Fedor", surname: "Fedorenko", date: "12.07.l993" },
      { id: "1", name: "Nikita", surname: "Kolesnechenko", date: "11.01.1967" },
      { id: "2", name: "Alexey", surname: "Stremanski", date: "09.06.1994" }
    );
    const headData = reactive (
      Object.keys(tableData)
    );
    const headProperties = {
      '--bg-color': '#1ea30c',
      '--font-color': "#000000",
    };
    return {
      tableData,
      headData,
      headProperties,
    }
  }
}
</script>

<style></style>
