<template>
<!-- <div class="nav-bar" :style="{height: screenHeight+'px'}"> -->
<div class="nav-bar" >
    <div class="left"><slot name="left"></slot></div>
    <div class="right"><slot name="right"></slot></div>
</div>
</template>

<script>
export default {
    name:"NavBar",
//     data(){
//         return {
//             screenWidth: document.body.clientWidth 
//         }
//     },
//     mounted(){
//           this.$nextTick(() => {
//         // 获取图片（或外层框）
//         let imgBox = this.$refs.imgBox
//         // 获取其宽度
//         let wImgbox = imgBox[0].getBoundingClientRect().width
//         // 设置其高度（以宽度的60%为例）
//         this.imgBox.height = 0.6 * wImgbox + 'px'
//     })
//             const that = this
//     window.onresize = () => {
//         return (() => {
//             window.screenWidth = document.body.clientWidth
//             that.screenWidth = window.screenWidth
//         })()
//     }
//     },
//     watch:{
//     screenWidth(val){
//         // 为了避免频繁触发resize函数导致页面卡顿，使用定时器
//         if(!this.timer){
//             // 一旦监听到的screenWidth值改变，就将其重新赋给data里的screenWidth
//             this.screenWidth = val
//             this.timer = true
//             let that = this
//             setTimeout(function(){
//                 // 打印screenWidth变化的值
//                 console.log(that.screenWidth)
//                 that.timer = false
//             },400)
//             }
//         }
//         },
// methods :{
// 			get_bodyHeight () {//动态获取浏览器高度
// 				const that = this
// 				window.onresize = () => {
// 					return (() => {
// 						window.fullHeight = document.documentElement.clientHeight
// 						that.fullHeight = window.fullHeight
// 					})()
// 				}
// 			}
// 		}
//  data(){
//      return{
//   screenHeight: document.body.clientHeight
//      }
// },
// mounted () {
//   const that = this
//   window.onresize = () => {
//     return (() => {
//        window.screenHeight = document.body.clientHeight
//        that.screenHeight = window.screenHeight
//     })()
//   }
// },
// watch: {
//       screenHeight (val) {
//         // 为了避免频繁触发resize函数导致页面卡顿，使用定时器
//         if (!this.timer) {
//           // 一旦监听到的screenWidth值改变，就将其重新赋给data里的screenWidth
//           this.screenHeight = val
//           this.timer = true
//           let that = this
//           setTimeout(function () {
//             // 打印screenWidth变化的值
//             console.log(that.screenHeight)
//             that.timer = false
//           }, 400)
//         }
//       }
//     }
}
</script>

<style scoped>
/* .nav-bar{
    display: flex;
    line-height: 24px;
    height: 24px;
    font-size: 18px;
    font-style: normal;
    box-shadow: 0 1px 1px rgba(100,100,100,.1)

} */
.left{
    width:10px;
    background-color: blue;
}
.right{
    flex:1;
    background-color:cornflowerblue;
}
</style>