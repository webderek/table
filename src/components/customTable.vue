<template>
  <table>
    <TableHead :tableData="tableData" :headProperties="headProperties">
    </TableHead>
    <DataTable v-for="item of tableData" :key="item">
      <template v-slot:id>
        <td class="data-item">{{ item.id }}</td>
      </template>
      <template v-slot:name>
        <td class="data-item">{{ item.name }}</td>
      </template>
      <template v-slot:surname>
        <td class="data-item">{{ item.surname }}</td>
      </template>
      <template v-slot:date>
        <td class="data-item">{{ item.date }}</td>
      </template>
    </DataTable>
  </table>
</template>

<script>
import TableHead from "./tableHead.vue";
import DataTable from "./dataTable.vue";
export default {
  name: "tableHead",
  components: {
    TableHead,
    DataTable,
  },
  props: {
    tableData: Object,
    headProperties: Object,
  },
  setup(props) {
    console.log(props.tableData);
  },
};
</script>

<style lang="scss" scoped>
table {
  border-spacing: 0 10px;
  font-family: "Open Sans", sans-serif;
  font-weight: bold;
}
.data {
  &-item {
    vertical-align: middle;
    padding: 10px;
    font-size: 14px;
    text-align: center;
    border-top: 2px solid #56433d;
    border-bottom: 2px solid #56433d;
    border-right: 2px solid #56433d;
  }
  &-item:first-child {
    border-left: 2px solid #56433d;
  }
  &-item:nth-child(2) {
    text-align: left;
  }
}
</style>
