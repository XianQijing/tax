<template>
  <div class="body">
    <div class="table">
      <template>
        <el-table
          :data="tableData"
          style="width: 100%"
          :cell-style="rowStyle"
          :header-cell-style="headerStyle"
          >
          <el-table-column
            prop="date"
            label="日期">
          </el-table-column>
          <el-table-column
            prop="name"
            label="姓名">
          </el-table-column>
          <el-table-column
            prop="address">
          </el-table-column>
        </el-table>
      </template>
    </div>

    <div class="pages">
      <el-pagination
        background
        layout="prev, pager, next"
        @current-change="handleCurrentChange"
        :total="total">
      </el-pagination>
    </div>
  </div>
</template>
<script>
export default {
  name: 'homeBody',
  data () {
    return {
      currentPage4: 4,
      total: 100,
      tableData: null
    }
  },
  methods: {
    rowStyle (row, rowIndex) {
      return 'border: none'
    },
    headerStyle (row, rowIndex) {
      return 'border:none; color: rgb(204, 204, 204);'
    },
    handleCurrentChange (val) {
      console.log(`当前页: ${val}`)
    },
    getData () {
      this.axios.get('http://192.168.1.128:80/select').then(res => {
        console.log(res)
      })
    }
  },
  mounted () {
    this.getData()
  }
}
</script>

<style scoped>
.body {
  background: #fafdff;
  padding: 42px;
}
.table {
  padding: 40px;
  background: white;
  border: 2px rgb(229, 244, 255) solid;
  height: calc(100% - 130px);
}
.el-table--fit {
  border: none;
}
.el-table--fit::before {
  height: 0;
}
.pages {
  float: right;
  padding: 20px 0 0 0;
}
</style>
