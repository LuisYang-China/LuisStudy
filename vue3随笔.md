# vue3随笔

### vue3属性

1. setup() vue3的入口函数，相当于以前的created 和beforecreated生命周期。

   其他生命周期函数在setup函数中调用顺序如下：

   ```js
   <script lang="ts">
   import { nextTick,onMounted,onBeforeMount } from 'vue'
   export default {
     name: "test",
     // 入口函数相当于之前的created和beforecreated生命周期
     setup(){
       nextTick(() =>{
         console.log('nextTick')
       })
       onMounted(() =>{
         console.log('onMounted')
       })
       onBeforeMount(() => {
         console.log('onBeforMount')
       })
       console.log('vue3')
     }
   }
   ```

   ------

   调用结果如下：

   ```
   vue3
   onBeforMount
   onMounted
   nextTick
   ```

2. 在vue3中是先引入函数后调用，跟之前vue版本区别很大。注：在vue3中不能直接声明数据，直接声明的数据非响应式，不会做出相应改变

   - ref 响应式数据。例：const num = ref(33)

   - reactive 复杂响应式数据，可定义多个数据源，推荐使用。例 const state = reactive({ Array:[1,2,3],text:'数据1' })

   - toRefs 将复杂响应式数据转化为ref数据。

   - wacth 监听属性，数据变化时调用，可以监听多个值

   - wacthEffect 监听属性，进页面时会触发一次，之后每次值改变也会触发，wacth的副作用函数

   - methods 事件集合，可以放置多个事件，return抛出

   - computed 计算属性，相当于执行一个函数并进行监听，当监听的值改变时，computed内的值也会做出相应改变

     代码如下：

     ```
     <script lang="ts">
     import {ref, toRefs, reactive, watchEffect, watch, computed} from 'vue'
     export default {
       name: 'HelloWorld',
       setup(){
         let myAge = ref(23)  // 响应式数据
         let myName = '杨小文' // 非响应式数据
         const state = reactive({
           // 复杂数据响应式
           hoppys:['中国象棋','js','css','html','滑雪']
         })
         const statel = reactive({
           // 可以定义多个数据源
           form:'福建福州',
           forms:'河南许昌'
         })
         watchEffect(() =>{
           // watch副作用函数，首次加载时会触发，值发生变化时也会触发
           console.log('年龄',myAge.value)
           console.log('爱好',state.hoppys)
         })
         let myLastAge = computed(() =>{
           return myAge.value + 1
         })
         setTimeout(() => {
           state.hoppys[1] = 'ts'
           myAge.value += 1
           myName = '不凡学院'
         },1000)
         watch([state.hoppys,myAge],newVal=>{ // 可以监听多个值
           console.log('newVal',newVal)
         })
         const methods = {
           ageAdd(){
             myAge.value += 1
           },
           ageDelect(){
             myAge.value = 0
           }
         }
         return {
           myName,
           myAge,
           ...toRefs(state), // 将reactive转化为ref
           statel,
           myLastAge,
           ...methods
         }
       }
     
     }
     </script>
     ```

     