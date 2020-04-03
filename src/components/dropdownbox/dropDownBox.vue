//创建Select.vue组件

<template>
  <div class="selects">
    <!-- 选择框 -->
    <div
      :class="{selects0show: !isshow,selects0hade: isshow}"
      class="selects0"
      @click="isshow=!isshow"
    >
      <p v-text="xz"></p>
      <!-- <img src="@/assets/home/z_x_jt.png" alt srcset /> -->
    </div>
    <!-- 下拉框大盒子 -->
    <div
      :class="{show: !isshow,hade: isshow,issel:num>=4}"
      class="sel"
      :style="{height:35*num+'px'}"
    >
      <!-- 下拉框 -->
      <div
        @click="cutValue(i)"
        :style="{display: num >=(i+1)?'block':'none'}"
        v-for="(item,i) in num"
        :key="i"
        v-text="sel[i]"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    //显示多少个下拉框
    num: {
      type: Number,
      required: true //必传
    }, 
    //下拉框显示的数据
    sel: {
      type: Array,
      required: true //必传
    }
  },
  data() {
    return {
      isshow: true, //控制下拉框显示及隐藏
      xz: "请选择" //默认展示的内容
    };
  },
  methods: {
    //点击换文字的方法
    cutValue(val) {
      this.isshow = true;
      this.xz = this.sel[val]; //拿到父组件传来的数据
      this.$emit("va", val, this.sel[val]);
    }
  }
};
</script>

<style lang="less" scoped>
//显示下拉框
.show {
  display: block;
}
//隐藏下拉框
.hade {
  display: none;
}
//点击时改变选择框的边框颜色
.selects0show {
  border: 1px solid #01be6e;
}
//恢复边框颜色
.selects0hade {
  border: 1px solid #e4e4e4;
}
.selects {
  width: 100%;
  height: 100%;
  .selects0 {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    p {
      line-height: 100%;
      display: inline;
      color: #666666;   //默认字体颜色
      font-size: 15px;  //默认字体大小
      padding-left: 10px;
    }
    img {
      margin-right: 10px;
      transform: translateY(-2px);
    }
  }
  //当下拉框数量超过4个时 使用固定高度
  .issel {
    height: 140px !important;
  }
  .sel {
    width: 100%;
    height: 140px;
    overflow: auto;
    border: 1px solid #01be6e; //下拉框边框颜色
    border-top: none;
    div {
      width: 100%;
      height: 35px;  //下拉框高度
      display: flex;
      justify-content: space-between;
      align-items: center;
      line-height: 35px;
      padding-left: 10px;
      background: white; //下拉框默认背景
    }
    //鼠标移到下拉框时的背景
    div:hover {
      background: #01be6e;  
      color: white;
    }
    .selects0:hover {
      background: white;
    }
  }
  //隐藏滚动条
  .sel::-webkit-scrollbar {
    display: none;
  }
}
</style>
