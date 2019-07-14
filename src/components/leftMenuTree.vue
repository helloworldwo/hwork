<!-- 左侧导航树 -->
<template>
  <div class='treeStyle'>
    <ul class="listStyle">
      <li>
        <i class="iconfont icon-dashboard"></i>
        <span slot="title">DASHBOARD</span>
      </li>
      <li>
        <i class="iconfont icon-sitemap"></i>
        <span slot="title">AGENT</span>
      </li>
      <li>
        <i class="iconfont icon-boat"></i>
        <span slot="title">MY CRUSE</span>
      </li>
      <li>
        <i class="iconfont icon-life-bouy"></i>
        <span slot="title">HELP</span>
      </li>
    </ul>
    <div class="testStyle">
      <p>History</p>
      <ul>
        <li v-for="(item,index) in [1,2,3,4,5,6,7]" :key="index">
          bjstdmngbgr{{index}}/Acceptance_test
        </li>
      </ul>

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
<style lang="less">
  .treeStyle {
    position: relative;
    height: 100%;
    background-color: #2d4054;


    .listStyle {
      margin: 0;
      padding-top: 15px;
    }

    .listStyle li:first-child {
      margin-top: 20px;
    }

    .listStyle li {
      height: 45px;
      color: #f3f3f3;
      list-style: none;
      margin-right: 15px;

      i {
        margin-right: 5px;
      }
    }

    .listStyle li:hover {
      color: #00b4cf;
      cursor: pointer;
    }

    .testStyle {
      position: absolute;
      bottom: 5px;
      overflow: hidden;

      p {
          margin: 0;
        font-size: 24px;
        color: #ccc;
        margin-left: 25px;
      }
      ul{
          margin:0;
      }

      ul li {
        font-size: 12px;
        color: #999;
        list-style:outside;
        line-height: 25px;
      }

      ul li:hover {
        color: #00b4cf
      }
    }
  }

</style>
