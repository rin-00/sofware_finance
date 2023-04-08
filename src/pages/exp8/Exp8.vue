<!-- 8.软件项目/产品的财务评价实验
包括: 净现值法、IRR 法、投资回收期法等 -->
<template>
<h1 class="title" >实验8 软件项目/产品的财务评价实验
      
      <span>  <el-button  class="guidance" type="primary" text ><el-icon size="25px"><Document /></el-icon>实验指导书下载</el-button></span> 
  </h1>
  <hr />
  <!-- <span> {{ test }}</span> -->
  <a-table :dataSource="dataSource" :columns="columns" />

</template>
  
  <script lang="ts">
    export default {
      name: 'Exp8',
      setup() {
        return {
          dataSource: [
            {
              key: '1',
              name: 'Mike',
              age: 32,
              address: '10 Downing Street',
            },
            {
              key: '2',
              name: 'John',
              age: 42,
              address: '10 Downing Street',
            },
          ],

          columns: [
            {
              title: 'Name',
              dataIndex: 'name',
              key: 'name',
            },
            {
              title: 'Age',
              dataIndex: 'age',
              key: 'age',
            },
            {
              title: 'Address',
              dataIndex: 'address',
              key: 'address',
            },
          ],
        };
      },
    };
  </script>
  
  <style scoped lang="less">
  .title{
    text-align:center;
    font-family: sans-serif;
    font-size:30px;
}
.secondtitle{
    text-indent: 2em;
    font-weight: bold;
    margin-left: 30px;
    margin-right: 30px;
}
.content{
    text-indent: 2em;
    margin-left: 20px;
    margin-right: 20px;
}
.guidance{
    position:absolute;
    right:50px;
    font-weight: bold;
}
</style>