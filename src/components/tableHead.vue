<template>
  <tr class="head" :style="headProperties">
    <th class="head-cell" v-for="item of headData" :key="item">
      {{ firstLetterToUpperCase(item) }}
    </th>
  </tr>
</template>

<script>
import { computed } from "@vue/reactivity";
import { firstLetterToUpperCase } from "../../utils/index";
export default {
  name: "tableHead",
  props: {
    tableData: Object,
    headProperties: Object,
  },
  setup(props) {
    const headData = computed(() => {
      return Object.keys(props.tableData[0]);
    });
    return {
      firstLetterToUpperCase,
      headData,
    };
  },
};
</script>

<style lang="scss" scoped>
.head {
  &-cell {
    padding: 10px 20px;
    background: var(--bg-color);
    color: var(--font-color);
    border-right: 2px solid var(--border-color);
    font-size: 15px;

    &:last-child {
      border-right: none;
    }
  }
}
th:first-child {
  text-align: left;
}
</style>
