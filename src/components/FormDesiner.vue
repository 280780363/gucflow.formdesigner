<template>
  <div>
    <table>
      <thead>
        <th>empty</th>
        <th></th>
      </thead>
      <tr></tr>
    </table>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      enums: {},
      tempData: {
        table: {
          colCount: 8,
          rowCount: 8
        }
      },
      cellData: [
        {
          row: 1,
          col: 1,
          content: {
            type: "text",
            value: "aaaa"
          }
        }
      ]
    };
  },
  methods: {
    addCol() {},
    addRow() {},
    delCol() {},
    delRow() {},
    mergeCell() {},
    resizeColWidth() {},
    resizeRowHeight() {},
    getColHeaderTitle(colIndex) {
      let last = String.fromCharCode((colIndex % 26 || 26) + 64);
      let i = Math.floor((colIndex - 1) / 26);
      let first = i == 0 ? "" : String.fromCharCode(i + 64);
      return first + last;
    }
  }
};
</script>
<style lang="less" scoped>
</style>
