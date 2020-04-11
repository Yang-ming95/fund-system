<template>
    <div class="hello">
      <div class="children" @click="say">
        我是子组件
        <div>
          父组件对我说：{{msg}}
        </div>
      </div>
  
    </div>
  </template>
  
  <script>
  
    export default {
        //父组件通过props属性传递进来的数据
        props: {
            msg: {
                type: String,
                default: () => {
                    return ''
                }
            }
        },
        data () {
          return {
              childrenSay: 'hello, parent'
          }
        },
  
        methods: {
            // 子组件通过emit方法触发父组件中定义好的函数，从而将子组件中的数据传递给父组件
            say(){
                this.$emit('say' , this.childrenSay);
            }
        }
    }
  </script>