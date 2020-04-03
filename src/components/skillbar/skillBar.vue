<template>
  <dash-child>
    <div class="list-item-skill">
      <input class="skill-title-name" v-model="dataTitle">
      <p class="desc">
        <span class="line">
          <span class="show" :style="{ width: dataPercent + '%', background: selectColor }"></span>
        </span>
        <span class="percent-wrapper">
          <input class="percent" type="text" name="percent" maxlength="2" v-model.number="dataPercent">%
        </span>
      </p>
    </div>
  </dash-child>
</template>
<script type="text/ecmascript-6">
  //import dashChild from '../dashChild/dashChild.vue';
  export default {
    components: {
      //dashChild
    },
    props: {
      title: {
        type: String,
        default: 'JavaScript'
      },
      percent: {
        type: Number,
        default: 80
      }
    },
    data() {
      return {
        dataTitle: this.title,
        dataPercent: this.percent,
        colors: ['#001f3f', '#0074D9', '#7FDBFF', '#39CCCC', '#3D9970',
          '#2ECC40', '#01FF70', '#FFDC00', '#FF851B', '#FF4136', '#85144b',
          '#F012BE', '#B10DC9', '#111111', '#AAAAAA', '#DDDDDD']
      };
    },
    computed: {
      selectColor: function () {
        let index = Math.floor(Math.random() * this.colors.length);
        return this.colors[index];
      }
    }
  };
</script>


 <style scoped>
 
</style>