<template>
    <CustomTable :tableData="tableData" :headProperties="headProperties" />
</template>

<script>
import { reactive } from "@vue/reactivity";
import { defineComponent } from "vue";
import CustomTable from "./components/customTable.vue";

export default defineComponent({
  name: "App",
  components: {
    CustomTable,
  },
  setup() {
    const tableData = reactive([
      { id: "0", name: "Fedor", surname: "Fedorenko", date: "12.07.l993" },
      { id: "1", name: "Nikita", surname: "Kolesnechenko", date: "11.01.1967" },
      { id: "2", name: "Alexey", surname: "Stremanski", date: "09.06.1994" },
    ]);
    const headProperties = {
      "--bg-color": "#1ea30c",
      "--font-color": "black",
      "--border-color": "#648545",
    };
    console.log(tableData);
    return {
      tableData,
      headProperties,
    };
  },
});
</script>

<style></style>
