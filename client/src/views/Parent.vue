<template>
    <div class="parent">
      我是父组件
      <!--父组件监听子组件触发的say方法，调用自己的parentSay方法-->
      <!--通过:msg将父组件的数据传递给子组件-->
      <children :msg="msg" @say="parentSay"></children>
      <button @click="changemsg">aaa</button>
    </div>
  </template>
  
  <script>
  
  import Children from '@/components/Children.vue'
  
  export default {
    data () {
      return {
        msg: 'hello, children'
      }
    },
  
    methods: {
        // 参数就是子组件传递出来的数据
        parentSay(msg){
            console.log(msg) // hello, parent
        },
        changemsg(){
          this.msg='change, children'
        }
    },
  
    // 引入子组件
    components:{
        children: Children
    }
  }
  </script>