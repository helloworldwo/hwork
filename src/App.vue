<template>
  <div id="app" style="width:1200px;border:1px solid #fff;height:100vh">
    <el-row style="height:55px">
      <div class="wrapLog">
        <img src="/static/logo/logo.svg" style="height:40px" />
      </div>
    </el-row>
    <div style="margin:0 auto;height:100%;width:80%">
      <el-row style="height:90%;width:100%;margin:0;" :gutter="20">
        <el-col :span="6" style="border:1px solid #fff;height:100%;">
          <leftMenuTree>left</leftMenuTree>
        </el-col>
        <el-col :span="18" style="border:1px solid #fff;height:100%;margin-top: 10px;">
          <rightContent>right</rightContent>
        </el-col>
      </el-row>

    </div>
  </div>
</template>

<script>
  import leftMenuTree from './components/leftMenuTree'
  import rightContent from './components/rightContent'
  export default {
    name: 'app',
    //import引入的组件需要注入到对象中才能使用
    components: {
      leftMenuTree,
      rightContent
    },
    data() {
      //这里存放数据
      return {

      };
    },
    //监听属性 类似于data概念
    computed: {},
    //监控data中的数据变化
    watch: {},
    //方法集合
    methods: {

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

<style>
  #app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    margin: 0 auto;
  }

  .wrapLog {
    margin: 0 auto;
    display: flex;
    height: 100%;
    justify-content: center;
    align-items: center;
    box-shadow: 0px 2px 10px 0px rgba(0, 0, 0, 0.1), 0 1px rgba(0, 0, 0, 0.1);
    background: #fafafa;
  }

</style>
