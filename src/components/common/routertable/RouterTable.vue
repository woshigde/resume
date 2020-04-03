<template>
<div>
    <el-table 
    :data="this.tableData"
    height="400px" 
    max-height="400px" 
    size="small"
    row-class-name="row"
    cell-class-name="column"
    :row-style="setRowStyle"
    :cell-style="setColumnStyle"
    :highlight-current-row="true"
    fit
    >
    <el-table-column
        v-for="(item, index) in tableLabel"
        :key="index" 
        :prop="item.prop" 
        :width="item.width" 
        :label="item.label">
        <template slot-scope="scope">
            <el-button type="text" size="small" @click="handleGoods(scope.row)" v-if="item.isOpera">{{scope.row[item.prop]}}</el-button>
            <div v-else>{{scope.row[item.prop]}}</div> 
        </template>
    </el-table-column>
</el-table>

</div>
</template>

<script>

export default {
    name:"RouterTable",
    props: {
     tableData: {
         type: Array,
         default: []
     },
     tableLabel: {
         type: Array,
         default: () => {
             return []
         }
     }
 }
}
</script>

<style scoped>

</style>