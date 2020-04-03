<template>
    <div class="tab-control">     
        <div class="icon" @click="show">
            <slot name="icon">
            <img src="../../../assets/img/leaf.svg" alt="">
            <!-- <TestSlot class="test-slow"></TestSlot> -->
                        <!-- <div class="test-slot">
            <TestSlot ></TestSlot>
            </div> -->
            </slot>
            <!-- <div class="test-slot">
            <TestSlot ></TestSlot>
            </div> -->
        </div>
            <!-- <TestSlot class="test-slow"></TestSlot> -->

            <!-- <div class="test-slot">
            <TestSlot ></TestSlot>
            </div> -->
        
        <div class="tab-control-item-show">
        <slot name="information">
        <div v-for="(item,index) in titles"
            class="tab-control-item" :class="{active: index===currentIndex}" 
            :style='styleObject'
            @click="itemClick(index)">
            <span>{{item}}</span>
        </div>
        </slot>
        </div>
    </div>
</template>

<script>
    //var widthPercent=this.titles.length
    import TestSlot from '../../testslot/TestSlot'

export default {
    name:"TabControl",
    //这里的导航栏只需要传文字
    components:{
        TestSlot
    },
    props:{
        titles:{
            type:Array,
            default(){
                return []
            }
        }
    },
    watch:{
        titles(val){
            this.titles=val;
           // this.getList()
        },
        deep:true
    },
    data(){
        return{
            currentIndex:0,
            widthPercent:this.titles.length,
            
            styleObject:{
                //  this.widthPercent
                    width:'900px',
                   // width:'100%',
                    //width: 1/(this.titles.length)*100+'%' ,
                    minWidth: 1/(this.titles.length)*100+'%' ,
                    maxWidth: 1/(this.titles.length)*100+'%' ,
                    flexGrow: 0,
                    flexShrink: 0,
                    //float:'left',
                    margin:'auto',
                    display:1,
                    overFlow:'hidden'
            }
        }
    }, 
    methods:{
        itemClick(index){
            this.currentIndex=index;
            //this.$emit()触发会被父级监控，同时也触发父级tabclick事件
            this.$emit('tabClick',index)
        },
        show(){
            console.log(1/(this.titles.length)*100+'%')
            console.log(this.widthPercent)
        }
    }
}
</script>

<style scoped>
.tab-control {
    display: flex;
    text-align: left;
    font-size:16px;
    background-color: #fff;
    font-style: normal;
    display: flex;
    height: 20px;
    /* position: relative; */
}
.icon{
    text-align: center;
    position: relative;
    vertical-align: middle;
    /* display:table-cell; */
    display: inline
}

.icon img{
    height: 16px;
    width: 40px;
    text-align: center;
    position: absolute;
    margin: auto;
    top: 0; left: 0; bottom: 0; right: 0; 
    /* display: inline-block */
}

.test-slot{
    margin-left: 20px;
    text-align: center;
    /* top: 0; left: 0; bottom: 0; right: 0;  */
    float: left;

    
}
/* .tab-control-item{
    width: 250px;
    height: 40px;
    line-height: 40px;
    float: left;
    margin-left: 40px

} */
.tab-control-item-show{
    width: 100%;
    /* width: calc(100%-40px); */
    display: flex;
    flex-wrap: wrap;
    float: left;
    margin-left: 40px
}
/* .tab-control-item{
    width: 30%;
    min-width: 30%;
    max-width: 30%;
    flex-grow: 0;
    flex-shrink: 0;
    
} */

.active{
    color: var(--color-high-text);
}

.active span{
    border-bottom: 3px solid var(--color-tint)
}

</style>



