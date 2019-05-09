<template>
  <div class="main">
    <ul>
      <!-- <li>
        <input type="text" :value='parentMessage'>
        <span class="icon">x</span>
      </li> -->
    </ul>
  </div>
</template>

<script type="text/javascript">
export default {
  name: 'Main',
  data() {
    return {

    }
  },
  props: ['parentMessage'],
  methods: {
    mainMethod:function () {
      var ul = document.querySelector('.main ul')
      var li=document.createElement('li');
        li.innerHTML='<input type="text" :value="parentMessage"><span class="icon">x</span>';
        ul.appendChild(li);   //  创造出 li
        var lis = document.querySelectorAll('.main ul li');
        lis.forEach(function(item,index){   // 创造的li
          item.style.width = "33.3%";
          item.style.height = "50px";
          item.style.margin = "0 auto 20px";
          item.style.listStyle = "none";   //  list-style  在这里写时就要 改成 listStyle
          item.onmouseover = function (){
            this.children[1].style.display = "block"
          };
          item.onmouseout = function (){
            this.children[1].style.display = "none"
          }
        })
        var inputs = document.querySelectorAll('.main ul li input');  //创造的 input
        inputs.forEach(function(item,index){   // 创造的li
          item.style.border = "1px solid #ccc";
          item.style.width = "90%";
          item.style.height = "100%";
          item.style.fontSize = "20px";
          item.style.paddingLeft = "6px";
          item.style.float = "left";
        })
        var spans = document.querySelectorAll('.main ul li span');    //创造的 span
        spans.forEach(function(item,index){   // 创造的li
          item.style.float = "right";
          item.style.lineHeight = "50px";
          item.style.fontSize = "34px";
          item.style.color = "red";
          item.style.cursor = "pointer";
           item.style.display = "none";  // 默认隐藏 鼠标移入li 时显示出来移除
        })
    }
  }
}
</script>

<style lang="less" scoped>
  .main {
    ul li {
      list-style: none;
      width: 33.3%;
      height: 50px;
      margin: 0 auto;
      input {
        border: 1px solid #ccc;
        width: 80%;
        height: 100%;
        font-size: 20px;
        padding-left: 6px;
      }
      .icon {
        float: right;
        line-height: 50px;
        font-size: 34px;
        color: red;
        cursor: pointer;
      }
    }
  }
</style>
