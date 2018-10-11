<template>
    <div>
        <table border="0">
            <colgroup>
                <col style="width: 50px;" />
                <col v-for="col in tableData.layoutData.cols" :key="col" :style="{width:col.width}" />
            </colgroup>
            <thead>
                <th></th>
                <th v-for="(col,index) in tableData.layoutData.cols" :key="col">{{getColHeaderTitle(index+1)}}</th>
            </thead>
            <tr v-for="(row,index) in tableData.layoutData.rows" :key="row" :style="{height:row.height}">
                <td>{{index}}</td>
                <th v-for="(col) in tableData.layoutData.cols" :key="col"></th>
            </tr>
        </table>
    </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      enums: {},
      tableData: {
        // 布局数据
        layoutData: {
          cols: [
            {
              width: "50px"
            },
            {
              width: "50px"
            },
            {
              width: "50px"
            },
            {
              width: "50px"
            },
            {
              width: "50px"
            },
            {
              width: "50px"
            },
            {
              width: "50px"
            },
            {
              width: "50px"
            }
          ],
          rows: [
            {
              height: "24px"
            },
            {
              height: "24px"
            },
            {
              height: "24px"
            },
            {
              height: "24px"
            },
            {
              height: "24px"
            },
            {
              height: "24px"
            },
            {
              height: "24px"
            },
            {
              height: "24px"
            }
          ]
        },
        // 单元格数据
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
      }
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
table {
  border-left: 1px solid red;
  border-top: 1px solid red;
}
table td,
th {
  line-height: 18px;
  border-bottom: 1px solid red;
  border-right: 1px solid red;
}
</style>
