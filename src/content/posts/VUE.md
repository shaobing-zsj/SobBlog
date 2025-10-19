---
title: vue+ajax
published: 2025-10-19
description: ''
image: ''
tags: []
category: '前端'
draft: false 
lang: 'zh-CN'
---



引入vue模块

```html
<script type="module">
  import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';
  createApp({
      data(){
          return {
              message:'hello vue';
          }
      }
  	}
  ).mount("#app");
</script>
```

插值表达式写法		{{	}}

vue指令

v-for

作用：列表渲染，遍历容器的元素或者对象的属性

语法：`<tr v-for="(item,index) in items" :key="item.id">{{item}}</tr>`

参数：

- items 为遍历的数组
- item 为遍历出来的元素
- index 为索引/下标，从0开始 ；可以省略，省略index语法： `v-for = "item in items"`

key：

- 作用：给元素添加的唯一标识，便于vue进行列表项的正确排序复用，提升渲染性能
- 推荐使用id作为key（唯一），不推荐使用index作为key（会变化，不对应）

注意：遍历的数组，必须在data中定义； 要想让哪个标签循环展示多次，就在哪个标签上使用 v-for 指令。

      <tbody>
        <tr v-for="(e, index) in emplist" :key="e.id">
            <td>{{e.name}}</td>
            <td>{{e.gender==1?'男':'女'}}</td>
            <td>
                <span v-if="emp.job === '1'">班主任</span>
                <span v-else-if="emp.job === '2'">讲师</span>
                <span v-else-if="emp.job === '3'">学工主管</span>
                <span v-else-if="emp.job === '4'">教研主管</span>
                <span v-else-if="emp.job === '5'">咨询师</span>
                <span v-else>其他</span>
            </td>
            <td>{{e.entrydate}}</td>
            <td>{{e.updatetime}}</td>
            <td class="btn-group"> 
                <button class="edit" v-on:click="handle">编辑</button>
                <button class="delete" v-on:click="handle">删除</button>
            </td>
      </tbody>
      <script type="module">
            import{createApp} from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';
            createApp({
                data(){
                    return{
                       emplist:[{
                       
                       },{
                       
                       }]
                    };
                }
            }).mount('#app');



v-bind

作用：动态为HTML标签绑定属性值，如设置href，src，style样式等。

语法：`v-bind:属性名="属性值"` `<img v-bind:src="item.image" width="30px">`

简化：`:属性名="属性值"` `<img :src="item.image" width="30px">`

注意：v-bind 所绑定的数据，必须在data中定义/或基于data中定义的数据而来。

#### `<td><img v-bind:src="e.image" :alt="e.name" class="avatar"></td>`



#### v-if & v-show

作用：这两类指令，都是用来控制元素的显示与隐藏的

v-if：

- 语法：v-if="表达式"，表达式值为 true，显示；false，隐藏
- 原理：基于条件判断，来控制创建或移除元素节点（条件渲染）
- 场景：要么显示，要么不显示，不频繁切换的场景
- 其它：可以配合 v-else-if / v-else 进行链式调用条件判断

v-show：

- 语法：v-show="表达式"，表达式值为 true，显示；false，隐藏
- 原理：基于CSS样式display来控制显示与隐藏
- 场景：频繁切换显示隐藏的场景

```
`  <td>
    <span v-if="emp.job === '1'">班主任</span>
    <span v-else-if="emp.job === '2'">讲师</span>
    <span v-else-if="emp.job === '3'">学工主管</span>
    <span v-else-if="emp.job === '4'">教研主管</span>
    <span v-else-if="emp.job === '5'">咨询师</span>
    <span v-else>其他</span>
  </td>`

`<td>
    <span v-show="emp.job === '1'">班主任</span>
    <span v-show="emp.job === '2'">讲师</span>
    <span v-show="emp.job === '3'">学工主管</span>
    <span v-show="emp.job === '4'">教研主管</span>
    <span v-show="emp.job === '5'">咨询师</span>
</td>`
```



#### v-model

- 作用：在表单元素上使用，双向数据绑定。可以方便的 获取 或 设置 表单项数据 
- 语法：`v-model="变量名"`
- 这里的双向数据绑定，是指 Vue中的数据变化，会影响视图中的数据展示 。 视图中的输入的数据变化，也会影响Vue的数据模型 。

```
`<input type="text" name="name" placeholder="姓名" v-model="searchEmp.name" />`
  <script type="module">
        import{createApp} from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';
        createApp({
            data(){
            return{
              searchEmp: {
                  name: '',
                  gender: '',
                  job: ''
                }
            }
        }).mount('#app');
```

v-on

作用：为html标签绑定事件（添加时间监听）

语法：

- `v-on:事件名="方法名"` 
- 简写为 `@事件名="…"` 
- `<input type="button" value="点我一下试试" v-on:click="handle">`
- `<input type="button" value="点我一下试试" @click="handle">`

      <button type="button" @click="search">查询</button>
      <script type="module">
            import{createApp} from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js';
            createApp({
                data(){
                    return{
      			method:{
      				handle(){
      					alert();
      				}
      			}
                    };
                }
            }).mount('#app');

