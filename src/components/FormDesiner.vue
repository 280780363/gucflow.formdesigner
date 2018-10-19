<template>
  <div>
    <table border="0">
      <colgroup>
        <col style="width: 50px;" />
        <col v-for="col in tableData.layou.cols" :key="col.title" :style="{width:col.width+'px'}" />
      </colgroup>
      <thead>
        <th></th>
        <th v-for="col in tableData.layout.cols" :key="col">{{col.title}}</th>
      </thead>
      <tr v-for="row in tableData.layout.rows" :key="row.title" :style="{height:row.height+'px'}">
        <td>{{row.title}}</td>
        <td v-for="(col) in tableData.layout.cols" :key="col.title">{{col.title}}{{row.title}}</td>
      </tr>
    </table>
  </div>
</template>
<script>
// 横向居中方式
let align = {
  left: "left",
  center: "center",
  right: "right"
};
//纵向居中方式
let vertical_align = {
  top: "top",
  middle: "middle",
  bottom: "bottom"
};
export default {
  components: {},
  data() {
    return {
      enums: { align, vertical_align },
      tableData: {
        // 布局数据
        layout: {
          cols: [
            {
              title: "A",
              width: 50
            },
            {
              title: "B",
              width: 50
            },
            {
              title: "C",
              width: 50
            },
            {
              title: "D",
              width: 50
            },
            {
              title: "E",
              width: 50
            },
            {
              title: "F",
              width: 50
            },
            {
              title: "H",
              width: 50
            },
            {
              title: "I",
              width: 50
            }
          ],
          rows: [
            {
              title: "1",
              height: 24
            },
            {
              title: "2",
              height: 24
            },
            {
              title: "3",
              height: 24
            },
            {
              title: "4",
              height: 24
            },
            {
              title: "5",
              height: 24
            },
            {
              title: "6",
              height: 24
            },
            {
              title: "7",
              height: 24
            },
            {
              title: "8",
              height: 24
            }
          ]
        },
        // 单元格数据
        cells: [
          {
            row: 1,
            col: 1,
            style: {},
            content: {}
          }
        ],
        // 合并的单元格
        mergeCells: [
          {
            beginCol: 1,
            beginRow: 1,
            endCol: 3,
            endRow: 3,
            content: {
              type: "text",
              value: "aaaa"
            },
            style: {
              border: {
                top: null,
                bottom: null,
                left: null,
                right: null
              },
              vertical_align: "",
              align: "",
              css: ""
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
    clear() {},
    cancelMergeCell() {},
    resizeColWidth() {},
    resizeRowHeight() {},
    getMergeArea(col, row) {
      return this.mergeArea.find(
        r =>
          col >= r.beginCol &&
          col <= r.endCol &&
          row >= r.beginRow &&
          row <= r.endRow
      );
    },
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
