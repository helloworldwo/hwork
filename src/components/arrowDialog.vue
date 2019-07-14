<!-- 带箭头的自定义弹框组件 -->
<template>
  <div class="arrowDialogBox-container">
    <div class="arrowDialogBox">
      <i class="iconfont icon-close dialogClose" @click.stop="closeDialog()"></i>
      <p class="title">Sparate mutiple name with commas</p>
      <el-input v-model="inputVal" placeholder="Input Value"></el-input>
      <div class="btn">
        <span class="wrapSpan" @click.stop="addBrowers()">
          <a>Add Resource</a>
        </span>
        <span class="wrapSpan" @click.stop="closeDialog()">
          <a>Cancel</a>
        </span>
      </div>
      <slot></slot>
    </div>
  </div>
</template>

<script>
  //这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
  //例如：import 《组件名称》 from '《组件路径》';

  export default {
    //import引入的组件需要注入到对象中才能使用
    components: {},
    data() {
      //这里存放数据
      return {
        inputVal: ''

      };
    },
    //监听属性 类似于data概念
    computed: {},
    //监控data中的数据变化
    watch: {},
    //方法集合
    methods: {
      closeDialog() {
        this.$emit('closeDialog', false);
      },
      addBrowers() {
        this.$emit('addBrower', this.inputVal);
        this.$emit('closeDialog', false);
      }
    },
    //生命周期 - 创建完成（可以访问当前this实例）
    created() {

    },
    //生命周期 - 挂载完成（可以访问DOM元素）
    mounted() {

    },
    beforeCreate() {}, //生命周期 - 创建之前
    beforeMount() {}, //生命周期 - 挂载之前
    beforeUpdate() {}, //生命周期 - 更新之前
    updated() {}, //生命周期 - 更新之后
    beforeDestroy() {}, //生命周期 - 销毁之前
    destroyed() {}, //生命周期 - 销毁完成
    activated() {}, //如果页面有keep-alive缓存功能，这个函数会触发
  }

</script>
<style lang="less" scoped>
  .arrowDialogBox {
    position: absolute;
    width: 560px;
    font-size: 90%;
    line-height: 1.5;
    padding: .3em;
    border-radius: .2em;
    border: 1px solid #00b4cf;
    margin-top: 10px;
    background: #fff;
    box-shadow: 0px 3px 5px rgba(#000, 0.3);
    z-index: 999;
  }

  .arrowDialogBox:before {
    /*给提示框描画出箭头*/
    content: "";
    position: absolute;
    top: -.41em;
    left: 1em;
    padding: .35em;
    /*画一个高为0.7em的正方形*/
    background: inherit;
    /*背景色和边框继承提示框的*/
    border: inherit;
    border-right: 0;
    /*去掉右和下边框*/
    border-bottom: 0;
    transform: rotate(45deg);
    /*旋转45度*/
  }

  .title {
    color: #000;
  }

  .btn {
    display: inline-flex;
    margin: 5px 0px;
    flex-direction: row;

    .wrapSpan {
      height: 30px;
      width: 150px;
      display: inline-flex;
      justify-items: center;
      align-items: center;
      padding-left: 5px;
    }

    span:first-child {
      background-color: #00b4cf;
    }

    span:last-child {
      background-color: #2d4054;
    }
  }

  .dialogClose {
    color: #00b4cf;
    position: absolute;
    top: 5px;
    right: 15px;
  }

</style>
