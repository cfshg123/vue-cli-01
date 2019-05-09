<template>
  <div class="header">
    <input id="text" type="text" placeholder="请输入..." value="" >
    <button @click="addFn" >添加</button>
    <Main :parentMessage="parentMessage" ref="mymain"></Main>
  </div>
</template>

<script>
import Main from './Main'
export default {
  name: 'Header',
  components: {
    Main
  },
  data () {
    return {
      parentMessage: ''
    }
  },
  methods: {
    addFn: function() {   // 添加功能
    this.$refs.mymain.mainMethod()
    console.log("父组件")

      // // ul.appendChild(str)
      // console.log(ul)
      // let textVal = document.getElementById("text").value;
      // this.parentMessage = textVal;
      // textVal = ' ';
      // document.getElementById("text").outerHTML = document.getElementById("text").outerHTML;   // 初始化输入的 input 的html

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
  .header {
    padding: 100px 0 10px;
    input {
      padding-left: 5px;
      width: 200px;
      height: 30px;
      margin-right: 10px;
    }
    button {
      width: 50px;
      height: 36px;
    }
    // .main {
    //   ul li {
    //     input {
    //       border: 1px solid #ccc;
    //       width: 80%;
    //       height: 100%;
    //       font-size: 20px;
    //       padding-left: 6px;
    //     }
    //     .icon {
    //       float: right;
    //       line-height: 50px;
    //       font-size: 34px;
    //       color: red;
    //       cursor: pointer;
    //     }
    //   }
    // }
  }
</style>
