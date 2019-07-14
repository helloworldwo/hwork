<!-- 右侧内容区域 -->
<template>
  <div class='wrapContent'>
    <div class="topList">
      <div class="build iconfont icon-cog">
        <span class="name">Building</span>
        <span class="number">3</span>
      </div>
      <div class="ldle iconfont icon-coffee">
        <span class="name">ldle</span>
        <span class="number">5</span>
      </div>
      <div class="all">
        <el-table :data="tableData" style="width: 100%">
          <el-table-column prop="date" label="ALL" width="80">
          </el-table-column>
          <el-table-column prop="name" label="PHYSICAL" width="100">
          </el-table-column>
          <el-table-column prop="address" label="VIRTUAL" width="100">
          </el-table-column>
        </el-table>
        <!-- <div class="phyVir">
          <span>ALL</span>
          <span>PHYSICAL</span>
          <span>VIRTUAL</span>
        </div>
        <div class="phyVir">
          <span>8</span>
          <span>4</span>
          <span>8</span>
        </div> -->
        <!-- <el-row :gutter="10">
          <el-col :span="8">ALL</el-col>
          <el-col :span="8">PHYSICAL</el-col>
          <el-col :span="8">VIRTUAL</el-col>
        </el-row>
        <el-row :gutter="10">
          <el-col :span="8">8</el-col>
          <el-col :span="8">4</el-col>
          <el-col :span="8">4</el-col>
        </el-row> -->
      </div>
    </div>
    <div class='middleSearch'>
      <div class="leftTips">
        <a style="border-bottom:2px solid #00b4cf;color:#00b4cf">ALL</a>
        <a>PHYSICAL</a>
        <a>VIRTUAL</a>
      </div>
      <div class="centerSearch">
        <el-input style="background-color:#f5f7fa" prefix-icon="icon-search" v-model="input21">
        </el-input>
      </div>
      <div class="RightManger">
        <i class="iconfont icon-th-list" style="color:#00b4cf"></i>
        <i class="iconfont icon-th-card"></i>
      </div>
    </div>
    <div class="bottomContent">
      <systemItem v-for="(item,index) in systemList" :key="index" :systemObj="item"></systemItem>
    </div>
  </div>
</template>

<script>
  //这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
  //例如：import 《组件名称》 from '《组件路径》';
  import systemItem from '../components/systemItem'
  export default {
    //import引入的组件需要注入到对象中才能使用
    components: {
      systemItem
    },
    data() {
      //这里存放数据
      return {
        input21: '',
        tableData: [{
          date: '8',
          name: '4',
          address: '8'
        }],
        systemList: [{
            img: 'windows.png',
            url: 'sdsdss.thoughtWorks.com',
            status: 'ldle',
            ip: '192.168.2.3',
            foloderName: '/var/lib/curse-agent',
            browerlist: ['firfox', 'safari', 'chrome', 'Ubuntu'],
            denyFlage: true
          },
          {
            img: 'windows.png',
            url: 'sdsdss.thoughtWorks.com',
            status: 'building',
            ip: '192.168.2.3',
            foloderName: '/var/lib/curse-agent',
            browerlist: ['firfox', 'safari', 'chrome', 'Ubuntu'],
            denyFlage: true
          },
          {
            img: 'ubuntu.png',
            url: 'sdsdss.thoughtWorks.com',
            status: 'building',
            ip: '192.168.2.3',
            foloderName: '/var/lib/curse-agent',
            browerlist: ['firfox', 'safari', 'chrome', 'Ubuntu'],
            denyFlage: true
          },
          {
            img: 'debin.png',
            url: 'sdsdss.thoughtWorks.com',
            status: 'building',
            ip: '192.168.2.3',
            foloderName: '/var/lib/curse-agent',
            browerlist: ['firfox', 'safari', 'chrome', 'Ubuntu'],
            denyFlage: true
          },
          {
            img: 'cent_os.png',
            url: 'sdsdss.thoughtWorks.com',
            status: 'ldle',
            ip: '192.168.2.3',
            foloderName: '/var/lib/curse-agent',
            browerlist: ['firfox', 'safari', 'chrome', 'Ubuntu'],
            denyFlage: true
          },
        ]

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
  @board: 1px solid #fff;

  .wrapContent {
    display: flex;
    height: 100%;
    width: 100%;
    flex-direction: column;

    .topList {
      flex: 2;
      border: @board;
      display: flex;
      flex-direction: row;

      >div {
        margin-right: 15px;
        border: @board;
        flex: 1;

        .name {
          font-size: 18px;
          position: absolute;
          margin-top: 15px;
          margin-left: 15px;
          top: 5px;
          left: 5px;
          font-weight: bold;
          color: #fff
        }

        .number {
          font-size: 48px;
          position: absolute;
          margin: 0px 10px 10px 0px;
          bottom: 5px;
          right: 5px;
          color: #fff
        }
      }

      div:nth-last-child(1) {
        margin-right: 0px;
      }

      .build {
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        animation: rotate 2s/r;
        background-color: #ff9a2a;
      }

      .ldle {
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        animation: rotate 2s/r;
        background-color: #7fbc39;
      }

      .all {
        background-color: #fff;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        font-size: 14px;

        .el-table {
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;

          td {
            border: none;
            font-weight: 900;
          }

          th {
            border: none;
            font-weight: 600;
          }
        }

        .phyVir {
          display: flex;
          span {
            display: inline-block;
            margin-left: 15px;
            width: 60px;
            flex: 1;
            font-size: 14px;
          }
        }
      }
    }

    .middleSearch {
      flex: 1;
      border: @board;
      display: flex;
      margin: 10px 0px;
      flex-direction: row;

      >div {
        border: @board;
      }

      .leftTips {
        flex: 1;
        height: 50px;
        ;
        line-height: 50px;
        font-size: 16px;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;

        a {
          flex: 1;
          font-size: 12px;
          cursor: pointer;
          display: inline-block;
          display: flex;
          justify-content: center;
          width: 30px;
          margin-right: 5px;
          border-right: 1px solid #e1e4e6;
        }

        a:hover {
          border-bottom-color: #00b4cf;
          border-bottom-width: 3px;
        }
      }

      .centerSearch {
        display: flex;
        justify-items: center;
        align-items: center;
      }

      .RightManger {
        flex: 1;
        display: flex;
        flex-direction: row-reverse;
        justify-items: center;
        align-items: center;

        i {
          margin-right: 10px;
        }
      }
    }

    .bottomContent {
      flex: 12;
      border: @board;
    }

    .topList .iconfont {
      font-size: 144px;
    }
  }

  .icon-cog:before,
  .icon-coffee:before {
    opacity: 0.2;
  }

</style>
