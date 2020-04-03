<template>
  <div class="app"><h2 style="text-align:center">个人简历</h2>
    <NavBar class="resume-nav"><div slot="right">个人信息</div></NavBar>
    <table><tr><td style="width:100%;height:4px;font-size:4px;border:0"> </td></tr></table>
  <!-- <router-table :tableData="tableData" :tableLabel="tableLabel"></router-table> -->
  <formtable :tableData="tableData" :tableStyle="{width:'100%'}" ></formtable>
    <table><tr><td style="width:100%;height:4px;font-size:4px;border:0"> </td></tr></table>


    <NavBar class="resume-nav"><div slot="right">教育背景</div></NavBar>
    <table><tr><td style="width:100%;height:4px;font-size:4px;border:0"> </td></tr></table>
    <TabControl class="tab-control" :titles="['北京邮电大学 / 硕士 ','北京邮电大学 / 硕士 ','北京邮电大学 / 硕士 ']"></TabControl>
    <p class="words">hahahahhhhhhhhhhhhhhhhhhhhhhhaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahahahahhhhhhhhhhhhhhhhhhhhhhhaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa</p>
    <p class="words">硕士期间以第一作者发表X篇论文，获得X项专利，绩点排名前X%硕士期间以第一作者发表X篇论文，获得X项专利，绩点排名前X%</p>
    <table><tr><td style="width:100%;height:4px;font-size:4px;border:0"> </td></tr></table>
    <TabControl class="tab-control" :titles="['北京邮电大学 / 硕士 ','北京邮电大学 / 硕士 ','北京邮电大学 / 硕士 ']"></TabControl>
    <p class="words">hahahahhhhhhhhhhhhhhhhhhhhhhhaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahahahahhhhhhhhhhhhhhhhhhhhhhhaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa</p>
    <p class="words">硕士期间以第一作者发表X篇论文，获得X项专利，绩点排名前X%硕士期间以第一作者发表X篇论文，获得X项专利，绩点排名前X%</p>
    <table><tr><td style="width:100%;height:4px;font-size:4px;border:0"> </td></tr></table>


    <NavBar class="resume-nav"><div slot="right">工作经历</div></NavBar>
    <table><tr><td style="width:100%;height:4px;font-size:4px;border:0"> </td></tr></table>
    <TabControl class="tab-control" :titles="['1999.08 ~ 2019.08','XXXX公司XX研发中心','（岗位：XX软件开发工程师）']">
      <div slot="icon" >   
            <!-- <img src="./assets/img/collect.svg" alt=""> -->
      </div>
      <!-- <div slot="infomation" :titles="['在阿里工作 ']">怎么回事</div> -->
    </TabControl>
    <!-- <TestSlot><div slot="second">为什么</div></TestSlot> -->
    <table><tr><td style="width:100%;height:2px;font-size:2px;border:0"> </td></tr></table>
    <TabControl class="tab-control1" :titles="obj" v-if="obj.length"><div slot="icon" ><img src="./assets/img/collect.svg" alt=""></div></TabControl>
    <TabControl class="tab-control1" :titles="['项目简介：一句话简述ABC项目的主要业务场景，让陌生人能一眼看懂']"><div slot="icon" ><img src="./assets/img/collect.svg" alt=""></div></TabControl>
    <TabControl class="tab-control1" :titles="['主要工作和业绩：']"><div slot="icon" ><img src="./assets/img/collect.svg" alt=""></div></TabControl>
    <TabControl class="tab-control2" :titles="['重点描述你在此项目负责了哪些工作，提出了什么样的方案，最终达到了什么样的结果，以及遇到的最有挑战性的技术难点，可分条列出。']"><div slot="icon" ><img src="./assets/img/collect.svg" alt=""></div></TabControl>
    <TabControl class="tab-control2" :titles="['技术栈：描述你在该项目中使用的技术栈，比如：XXX / XXX / XXX …']"><div slot="icon" ><img src="./assets/img/collect.svg" alt=""></div></TabControl>
  

    <TestSlot @func="getMsg" class="test-slot"></TestSlot>

    <dropDownBox class="selects" @va="childValue" :num="count" :sel="sel">下拉框</dropDownBox>

    <!-- <button>{{getMsg()}}</button> -->

<!-- <button @func="getMsg">测试文本框输入内容</button> -->


  </div>
</template>

<script>
import NavBar from './components/common/navbar/NavBar'
import RouterTable from './components/common/routertable/RouterTable'
import formtable from './components/common/routertable/formtable'
import TabControl from './components/common/tabControl/TabControl'
//import skillBar from './components/skillbar/skillBar'
import TestSlot from './components/testslot/TestSlot'
import dropDownBox from './components/dropdownbox/dropDownBox'

export default {
  name: 'App',
  components: {
    NavBar,
    RouterTable,
    formtable,
    TabControl,
    //skillBar
    TestSlot,
    dropDownBox

  },
  // props:{
  //   msg:{
  //     type:String,
  //     default(){
  //       return '没有收到'
  //     }
  //   }
  // },
  props:['getInfo'],
data() {
	return {
		// tableLabel: [
    //                   {label: '', width: '40', prop: 'id'},
    //                   {label: '农户名称', width: '', prop: 'name', isOpera: true},
    //                   {label: '所属中心店', width: '', prop: 'shop', isOpera: true},
    //           ],
		// tableData: [
    //                {
    //                    id: 1,
    //                    name: '中国男',
    //                    shop: '阳光超市',
    //                    sex: '男',
    //                    phone: 18383929383,
    //                    area: '华北',
    //                    acreage: 90,
    //                    quantity: 444,
    //                    money: 34534,
    //                    add: '是'
    //                },

    //            ]
      tableData: [
        {key: '单号', value: '1001'},
        {key: '商品名称', value: '篮球'},
        {key: '价格', value: '120.00'},
        {key: '订单日期', value: '2017-03-01'},
        {key: '付款方式', value: '在线支付'},
        {key: '收货地址', value: '北京市海淀区西北旺镇'},
      ],
     msg:'this is msg',
      //arr:[]
    obj:[],

    sel:['男','女'], //下拉框的内容
    count:2, //下拉框条数
	}
},
// watch:{
//   getInfo(data){
//     this.msg=data
//     var obj=(this.msg || "").trim().split(/\s+/)
//     //return obj
//     this.info=obj
//   }
// },

// watch:{
//     getMsg(data){
//       this.msg=data
//       // console.log(this.msg)
//       // console.log(typeof(this.msg))
//       //console.log(this.msg.trim().split(/\s+/))
//       // console.log(typeof(this.msg.trim().split(/\s+/)))
//       var obj=(this.msg || "").trim().split(/\s+/)
//       console.log(obj.length)
//       //console.log(obj[0])
//       //console.log(typeof([1,2,3]))
//       // var arr=[]
//       // for(var i in obj){
//       //   arr.push(obj[i])s
//       // }
//     //   // console.log(typeof(arr))
//       var arr=['技术','现金']
//       console.log(arr[0])
//       return obj
//     }
// },
methods:{
    getMsg(data){
      this.msg=data
      // console.log(this.msg)
      // console.log(typeof(this.msg))
      //console.log(this.msg.trim().split(/\s+/))
      // console.log(typeof(this.msg.trim().split(/\s+/)))
      this.obj=(this.msg || "").trim().split(/\s+/)
     //this.obj=['haha','heheh','xixi']
     // console.log(obj[1])
      //console.log(obj[0])
      //console.log(typeof([1,2,3]))
      // var arr=[]
      // for(var i in obj){
      //   arr.push(obj[i])
      // }
    console.log(this.obj)
    console.log(this.obj.length)
     // console.log(obj.length)
      // console.log(arr[0])
      //return obj
    },

    childValue(index,val){
      console.log(index,val)
    }
}
}

</script>

<style scoped> 
  @import "./assets/css/base.css";
  /* .app{
    border: 1px solid blue;
    height: 300px;
  } */
  .resume-nav{
    display: flex;
    line-height: 24px;
    height: 24px;
    font-size: 18px;
    font-style: normal;
    box-shadow: 0 1px 1px rgba(100,100,100,.1);

}

  .tab-control1{
    text-align: left;
    /* height: 44px; */
    font-size: 16px;
    font-style: normal;
    width: 100%;
    background-color: red;
    margin: 3px auto;

  }
.words{
  text-indent:6em;
  /* overflow: hidden; */
  /* width: 100%; */
  
text-align: justify;

text-justify: newspaper;

word-break: break-all;
margin: 3px auto

}

.tab-control2{
      text-align: left;
    /* height: 44px; */
    font-size: 16px;
    font-style: normal;
    width: 100%-20px;
    background-color: greenyellow;
    margin: 3px auto;
    margin-left: 28px
}

.test-slot{
  text-align: center
}

.selects{
  width: 200px;
  height:35px;
  z-index: 1000
}
</style>
