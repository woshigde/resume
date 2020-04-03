<template>
<div>
      <table class="mailTable" :style="styleObject" v-if="s_showByRow">
    <tr v-for="index in rowCount">
      <td class="column">{{tableData[index*2-2].key}}</td>
      <td class="column1">{{tableData[index*2-2].value}}</td>
      <td class="column">{{tableData[index*2-1] !== undefined ? tableData[index*2-1].key : ''}}</td>
      <td class="column1">{{tableData[index*2-1] !== undefined ? tableData[index*2-1].value : ''}}</td>
    </tr>
  </table>
  <table class="mailTable" :style="styleObject" v-else>
    <tr v-for="index in rowCount">
      <td class="column">{{tableData[index-1].key}}</td>
      <td>{{tableData[index-1].value}}</td>
      <td class="column">{{tableData[rowCount+index-1] !== undefined ? tableData[rowCount+index-1].key : ''}}</td>
      <td>{{tableData[rowCount+index-1] !== undefined ? tableData[rowCount+index-1].value : ''}}</td>
    </tr>
  </table>

</div>
</template>

<script>
export default {
    name:"formtable",
     data() {
    return {
      styleObject: {},
      s_showByRow: true,
    };
  },
  props: ['tableData', 'tableStyle', 'showByRow'],
  computed: {
    rowCount: function() {
      return Math.ceil(this.tableData.length/2);
    }
  },
  created() {
    this.styleObject = this.tableStyle;
    if(this.showByRow !== undefined){
      this.s_showByRow = this.showByRow;
    }
  },
}
</script>

<style scoped>
.mailTable{
  /* margin-left: 500px */
  vertical-align: middle;
  width: 100%;

}
.column{
  background-color: aquamarine;
  height: 10px;
  width: 80px;
  text-align: center;
}

.column1{
  height: 10px;
  width:382.5px;
}


</style>