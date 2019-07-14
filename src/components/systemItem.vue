<!-- 设备信息 -->
<template>
  <div class='wrapSytem'>
    <div class="imgSys">
      <img :src=imgUrl />
    </div>
    <div class="contentSys">
      <div class="topSys">
        <span class="urlStyle">
          <i class="iconfont icon-desktop"></i>
          <span style="color:#00b4cf">{{contentObj.url}}</span>
        </span>
        <span class="statusStyle">
          <span :class="contentObj.status == 'ldle'?'ldleStlye':'buildStyle'">{{contentObj.status}}</span>
        </span>
        <span class="ipStyle">
          <i class="iconfont icon-info"></i>
          {{contentObj.ip}}
        </span>
        <span class="folderStyle">
          <i class="iconfont icon-folder"></i>
          {{contentObj.foloderName}}
        </span>
      </div>
      <div class="bottomSys">
        <a class="addStyle">
          <i class="iconfont icon-plus addPlus" @click="addBrower">
            <arrowDialog v-if="dialogShow" @closeDialog=closeDialog @addBrower=addBrowerVal
              style="position: absolute;top: 18px;left: -15px;"></arrowDialog>
          </i>
          <span v-for="(item,index) in sysBrowerlist" :key="index">
            {{item}}
            <i class="iconfont icon-trash" @click="delBrower(item,index)"></i>
          </span>
        </a>
        <a class="denyStyle">
          <i class="iconfont icon-deny">Deny</i>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
  import arrowDialog from './arrowDialog'
  //这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
  //例如：import 《组件名称》 from '《组件路径》';

  export default {
    //import引入的组件需要注入到对象中才能使用
    components: {
      arrowDialog
    },
    props: {
      systemObj: {
        type: Object
      }

    },
    data() {
      //这里存放数据
      return {
        contentObj: this.systemObj,
        dialogShow: false
      };
    },
    //监听属性 类似于data概念
    computed: {
      imgUrl() {
        return '/static/osIcons/' + this.contentObj.img;
      },
      sysBrowerlist() {
        return this.contentObj.browerlist;
      }
    },
    //监控data中的数据变化
    watch: {
      dialogShow(newVal, oldVa) {
        debugger
        console.log(newVal);
      }
    },
    //方法集合
    methods: {
      delBrower(item, index) {
        if (this.sysBrowerlist.length > 0) {
          this.sysBrowerlist.splice(index, 1);
        }
      },

      addBrower() {
        this.dialogShow = true;
      },

      closeDialog(flage) {
        this.dialogShow = flage;
      },

      addBrowerVal(val) {
        this.sysBrowerlist.push(val);
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
<style lang="less">
  @board: 1px solid #fff;

  .wrapSytem {
    height: 100px;
    width: 100%;
    background-color: #fff;
    border: @board;
    display: flex;
    align-items: center;
  }

  .imgSys {
    display: flex;
    align-items: center;
    border: @board;
    margin-right: 5px;

    img {
      width: 80px;
    }
  }

  .contentSys {
    border: @board;
    flex: 1;
    display: flex;
    flex-direction: column;
    height: 100%;

    >div {
      flex: 1;
      border: @board;
    }

    .topSys {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;

      >span:not(.ipStyle) {
        flex: 1;
        border: @board;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 14px;

        i {

          margin-right: 5px;
        }
      }

      .ipStyle {
        border: @board;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 14px;
        width: 100px;
      }
    }

    .bottomSys {
      display: flex;
      flex-direction: row;

      >div {
        border: @board;
      }

      .addStyle {
        flex: 1;
        display: flex;
        align-items: center;

        .addPlus {
          position: relative;
          font-size: 18px;
          display: flex;
          background-color: #00b4cf;
          color: #fff;
          margin-left: 5px;
          margin-right: 5px;
          cursor: pointer;
        }

        span {
          background-color: #efefef;
          margin-left: 5px;
          color: #000;
          display: flex;
          align-items: center;

          i {
            margin-left: 5px;
            cursor: pointer;
          }
        }
      }

      .denyStyle {
        width: 70px;
        height: 30px;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        background-color: #00b4cf;

        i {
          display: flex;
          justify-content: center;
          align-items: center;
          font-size: 14px;
          height: 30px;
          color: #fff;
        }
      }

      .denyStyle:hover {
        background-color: #01869a;
        cursor: pointer;
      }
    }
  }

  .ldleStlye {
    color: #fff;
    background-color: #7fbe39;
  }

  .buildStyle {
    color: #fff;
    background-color: #ff9a2a;
  }

</style>
