<!-- 8.软件项目/产品的财务评价实验
包括: 净现值法、IRR 法、投资回收期法等 -->
<template>
  <h1 class="title" >实验8 软件项目/产品的财务评价实验
        
        <span>  <el-button  class="guidance" type="primary" text ><el-icon size="25px"><Document /></el-icon>实验指导书下载</el-button></span> 
    </h1>
    <hr />
    <!-- <span> {{ test }}</span> -->
    <h2>一、实验目的</h2>
    <p class="content">基于业务目标及市场信息的分析，设计课程设计项目的营销策略和软件定价策略方法，构建课程设计项目财务评价模型，根据本地区及实验期内的经济参数，通过本实验测算课程设计项目盈利能力和项目生存能力。
    </p>
    <h2>二、实验步骤</h2>
    <h3>1.前置输入</h3>
    <p class="content">本实验中，独立项目的生命周期设定为
    <a-input-number id="inputNumber" v-model:value="year" :bordered="false" :min="1" :max="10" />
    年</p>
    <h3>2.项目现金流入</h3>
    <p class="content">项目的现金流入包括独立方案的年收入，其中，独立方案是指各工程项目方案的现金流是独立的、不相关，而且任何一个方案的采用与否都不会对是否采纳其他方案的决策产生影响。例如:阿里集团的淘宝和闲鱼，分别投资开发各自平台新产品方案，如果选择某个方案，不会影响到另一个方案，则这两个方案就是独立方案。请按照下列表格填写项目每年的现金流入：</p>
    <a-table :columns="columns_1" :data-source="Input">
        <template #bodyCell="{ column,record,index}">
            <template v-if="column.dataIndex === 'year0'">
              <template v-if="record.project === '独立方案年收入'">
                <a-input v-model:value="record.input0" style="width:100px;"/>
              </template> 
              <template v-if="record.project === '其他'">
                <a-input v-model:value="record.other_input0" style="width:100px;"/>
              </template>
            </template>
            <template v-if="column.dataIndex === 'year1'">
              <template v-if="record.project === '独立方案年收入'">
                <a-input v-model:value="record.input1" style="width:100px;"/>
              </template>
              <template v-if="record.project === '其他'">
                <a-input v-model:value="record.other_input1" style="width:100px;"/>
              </template> 
            </template>
            <template v-if="column.dataIndex === 'year2'">
              <template v-if="record.project === '独立方案年收入'">
                <a-input v-model:value="record.input2" style="width:100px;"/>
              </template>
              <template v-if="record.project === '其他'">
                <a-input v-model:value="record.other_input2" style="width:100px;"/>
              </template> 
            </template>
            <template v-if="column.dataIndex === 'year3'"> 
              <template v-if="record.project === '独立方案年收入'">
                <a-input v-model:value="record.input3" style="width:100px;"/>
              </template>
              <template v-if="record.project === '其他'">
                <a-input v-model:value="record.other_input3" style="width:100px;"/>
              </template> 
            </template>
            <template v-if="column.dataIndex === 'year4'">
              <template v-if="record.project === '独立方案年收入'">
                <a-input v-model:value="record.input4" style="width:100px;"/>
              </template>
              <template v-if="record.project === '其他'">
                <a-input v-model:value="record.other_input4" style="width:100px;"/>
              </template> 
            </template>
            <template v-if="column.dataIndex === 'year5'">
              <template v-if="record.project === '独立方案年收入'">
                <a-input v-model:value="record.input5" style="width:100px;"/>
              </template>
              <template v-if="record.project === '其他'">
                <a-input v-model:value="record.other_input5" style="width:100px;"/>
              </template> 
            </template>
        </template> 
      </a-table>
    <h3>3.项目现金流出</h3>
    <p class="content">项目的现金流出包括直接人员成本、非直接人员成本、直接运维成本、非直接运维成本和其他。
                      直接人员成本指员工的直接所得：包括工资、奖金、加班费、红利、职务津贴、遣散补偿等。
                      非直接人员成本指项目以外的其他相关公司的管理人员、辅助部门的人员工资、奖金、福利的分摊。
                      直接运维成本指硬件成本和对软件进行运维花费的成本。
                      非直接运维成本指非硬件成本。其他是除人员成本和运维成本外多余的花费。</p>
  
    <p class="content">请按照下列表格填写项目每年的现金流出：
    </p>
    <a-table :columns="columns_1" :data-source="Output">
    <template #bodyCell="{ column, record, index }">
      <template v-if="column.dataIndex === 'year0'">
        <template v-if ="record.project === '直接人力成本'">
          <a-input v-model:value="record.d_labour0" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接人力成本'">
          <a-input v-model:value="record.i_labour0" style="width:100px;" />
        </template>
        <template v-if="record.project === '直接运维成本'">
          <a-input v-model:value="record.d_operation0" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接运维成本'">
          <a-input v-model:value="record.i_operation0" style="width:100px;" />
        </template>
        <template v-if="record.project === '其他'">
          <a-input v-model:value="record.other0" style="width:100px;" />
        </template>
      </template>

      <template v-if="column.dataIndex === 'year1'">
        <template v-if="record.project === '直接人力成本'">
          <a-input v-model:value="record.d_labour1" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接人力成本'">
          <a-input v-model:value="record.i_labour1" style="width:100px;" />
        </template>
        <template v-if="record.project === '直接运维成本'">
          <a-input v-model:value="record.d_operation1" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接运维成本'">
          <a-input v-model:value="record.i_operation1" style="width:100px;" />
        </template>
        <template v-if="record.project === '其他'">
          <a-input v-model:value="record.other1" style="width:100px;" />
        </template>
      </template>

      <template v-if="column.dataIndex === 'year2'">
        <template v-if="record.project === '直接人力成本'">
          <a-input v-model:value="record.d_labour2" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接人力成本'">
          <a-input v-model:value="record.i_labour2" style="width:100px;" />
        </template>
        <template v-if="record.project === '直接运维成本'">
          <a-input v-model:value="record.d_operation2" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接运维成本'">
          <a-input v-model:value="record.i_labour2" style="width:100px;" />
        </template>
        <template v-if="record.project === '其他'">
          <a-input v-model:value="record.other2" style="width:100px;" />
        </template>
      </template>

      <template v-if="column.dataIndex === 'year3'">
        <template v-if="record.project === '直接人力成本'">
          <a-input v-model:value="record.d_labour3" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接人力成本'">
          <a-input v-model:value="record.i_labour3" style="width:100px;" />
        </template>
        <template v-if="record.project === '直接运维成本'">
          <a-input v-model:value="record.d_operation3" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接运维成本'">
          <a-input v-model:value="record.i_operation3" style="width:100px;" />
        </template>
        <template v-if="record.project === '其他'">
          <a-input v-model:value="record.other3" style="width:100px;" />
        </template>
      </template>

      <template v-if="column.dataIndex === 'year4'">
        <template v-if="record.project === '直接人力成本'">
          <a-input v-model:value="record.d_labour4" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接人力成本'">
          <a-input v-model:value="record.i_labour4" style="width:100px;" />
        </template>
        <template v-if="record.project === '直接运维成本'">
          <a-input v-model:value="record.d_operation4" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接运维成本'">
          <a-input v-model:value="record.i_operation4" style="width:100px;" />
        </template>
        <template v-if="record.project === '其他'">
          <a-input v-model:value="record.other4" style="width:100px;" />
        </template>
      </template>

      <template v-if="column.dataIndex === 'year5'">
        <template v-if="record.project === '直接人力成本'">
          <a-input v-model:value="record.d_labour5" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接人力成本'">
          <a-input v-model:value="record.i_labour5" style="width:100px;" />
        </template>
        <template v-if="record.project === '直接运维成本'">
          <a-input v-model:value="record.d_operation5" style="width:100px;" />
        </template>
        <template v-if="record.project === '间接运维成本'">
          <a-input v-model:value="record.i_operation5" style="width:100px;" />
        </template>
        <template v-if="record.project === '其他'">
          <a-input v-model:value="record.other5" style="width:100px;" />
        </template>
      </template>

    </template>
  </a-table>
    <h3>4.项目净现金流量</h3>
    <p class="content">根据1和2中得到的现金流入和现金流出计算净现金流量和累计净现金流量；</p>
    <p class="content">净现金流量是现金流量表中的一个指标，是指一定时期内，现金及现金等价物的流入（收入）减去流出（支出）的余额（净收入或净支出），反映了企业本期内净增加或净减少的现金及现金等价数额。</p>
    <p class="formula">某一年度的净现金流量=现金流入量-现金流出量。</p>
    <p class="content">根据当年的现值系数计算净现金流量（现值）和累计净现金流量（现值）。
  净现金流量现值为现金流入扣除现金流出的净额按照一定的折现率折现至评估时点的现值，净现金流量总现值是指未来各期现金净流量的现值之和，即未来现金流入现值与未来现金流出现值差额，也称为净现值。
  </p>
  <p class="formula">第n年的净现金流量现值=第n年的净现金流量×现值系数  </p>
    <a-table :columns="columns_1" :data-source="netCashFlow">
        <template #bodyCell="{ column,record,index}">
            <template v-if="column.dataIndex === 'year0'">
              <template v-if="record.project === '净现金流量'">
                <a-input v-model:value="record.F0" style="width:100px;"/>
              </template> 
              <template v-if="record.project === '净现金流量(现值)'">
                <a-input v-model:value="record.P0" style="width:100px;"/>
              </template> 
            </template>
            <template v-if="column.dataIndex === 'year1'">
              <template v-if="record.project === '净现金流量'">
                <a-input v-model:value="record.F1" style="width:100px;"/>
              </template> 
              <template v-if="record.project === '净现金流量(现值)'">
                <a-input v-model:value="record.P1" style="width:100px;"/>
              </template> 
            </template>
            <template v-if="column.dataIndex === 'year2'">
              <template v-if="record.project === '净现金流量'">
                <a-input v-model:value="record.F2" style="width:100px;"/>
              </template> 
              <template v-if="record.project === '净现金流量(现值)'">
                <a-input v-model:value="record.P2" style="width:100px;"/>
              </template> 
            </template>

            <template v-if="column.dataIndex === 'year3'">
              <template v-if="record.project === '净现金流量'">
                <a-input v-model:value="record.F3" style="width:100px;"/>
              </template> 
              <template v-if="record.project === '净现金流量(现值)'">
                <a-input v-model:value="record.P3" style="width:100px;"/>
              </template> 
            </template>

            <template v-if="column.dataIndex === 'year4'">
              <template v-if="record.project === '净现金流量'">
                <a-input v-model:value="record.F4" style="width:100px;"/>
              </template> 
              <template v-if="record.project === '净现金流量(现值)'">
                <a-input v-model:value="record.P4" style="width:100px;"/>
              </template> 
            </template>

            <template v-if="column.dataIndex === 'year5'">
              <template v-if="record.project === '净现金流量'">
                <a-input v-model:value="record.F5" style="width:100px;"/>
              </template> 
              <template v-if="record.project === '净现金流量(现值)'">
                <a-input v-model:value="record.P5" style="width:100px;"/>
              </template> 
            </template>
        </template> 
    </a-table>
    <h3>5.项目指标</h3>
    <p class="content">根据所提取的财务评价所需基础数据进行项目财务分析，重在考察项目盈利能力是否能够满足要求。编制项目资本金现金流量表，计算项目资本金财务内部收益率IRR、净现值NPV以及动态投资回收期（年），考察项目资本金可获得的收益水平。
    </p>
    <p class="content">1. 项目资本金财务内部收益率IRR是指在整个计算期内净现值等于零时所对应的折现率,公式如下：</p>
    <p class="content">其中，IRR为内部收益率，（CI-CO）t为第t年净现金流量，n为方案寿命期。</p>
    <p class="content">2. 净现值NPV是指按照一定的折现率（通常为基准折现率ic），将各年的净现金流量折现到同一时点（通常是期初时点）的现值之和,公式如下：</p>
    <p class="content">（CI-CO）t为第t年的净现金流量，n为方案寿命期，ic为设定的折现率（基准收益率）。</p>
    <p class="content">3. 动态投资回收期（年）是指按照设定的基准收益率ic回收全部投资所需的时间,公式如下：</p>
    <p class="content">其中，DPP为动态投资回收期、（CI-CO）t为第t年净现金流量，ic为设定的基准收益率。</p>
    <p class="content">根据计算，本项目的财务指标如下</p>
    <a-table :dataSource="Index" :columns="columns_2" />
    <p class="content">根据上述步骤，汇总编制出的项目资本金现金流量表，计算出的项目资本金财务内部收益率IRR、净现值NPV以及动态投资回收期（年），考察项目资本金可获得的收益水平，综合判断项目的财务状况，并且做出评价。
    </p>
  
  </template>
    
    <script lang="ts">
      import { defineComponent, ref } from 'vue';
       export default{
        name: 'Exp8',
        setup() {
          const year = ref<number>(5);
          return {
            year,
          }
        },
          data(){
            return {
            Input: [
              {
                key: '1',
                number: '1',
                project: '现金流入',
                year0: 500,
                year1: 500,
                year2: 500,
                year3: 500,
                year4: 500,
                year5: 500,                  
              },
              {
                key: '2',
                number: '1.1',
                project: '独立方案年收入',
                year0: 500,
                year1: 500,
                year2: 500,
                year3: 500,
                year4: 500,
                year5: 500,                 
              },
              {
                key: '2',
                number: '1.2',
                project: '其他',
                year0: "",
                year1: "",
                year2: "",
                year3: "",
                year4: "",
                year5: "",                 
              },
            ],
            Output: [
              {
                key: '1',
                number: '2',
                project: '现金流出',
                year0: 300,
                year1: 310,
                year2: 320,
                year3: 330,
                year4: 340,
                year5: 350,                 
              },
              {
                key: '2',
                number: '2.1',
                project: '直接人力成本',
                year0: "",
                year1: "",
                year2: "",
                year3: "",
                year4: "",
                year5: "",                  
              },
              {
                key: '3',
                number: '2.2',
                project: '间接人力成本',
                year0: "",
                year1: "",
                year2: "",
                year3: "",
                year4: "",
                year5: "",                 
              },
              {
                key: '4',
                number: '2.3',
                project: '直接运维成本',
                year0: "",
                year1: "",
                year2: "",
                year3: "",
                year4: "",
                year5: "",                 
              },
              {
                key: '5',
                number: '2.4',
                project: '间接运维成本',
                year0: "",
                year1: "",
                year2: "",
                year3: "",
                year4: "",
                year5: "",               
              },
              {
                key: '6',
                number: '2.5',
                project: '其他',
                year0: "",
                year1: "",
                year2: "",
                year3: "",
                year4: "",
                year5: "",               
              },
            ],
            netCashFlow:[
            {
                key: '3',
                number: '3',
                project: '净现金流量',
                year0: "",
                year1: "",
                year2: "",
                year3: "",
                year4: "",
                year5: "",                  
              },
              {
                key: '3',
                number: '3.1',
                project: '累计净现金流量',
                year0: "",
                year1: "",
                year2: "",
                year3: "",
                year4: "",
                year5: "",                  
              },
              {
                key: '4',
                number: '4',
                project: '净现金流量(现值)',
                year0: "",
                year1: "",
                year2: "",
                year3: "",
                year4: "",
                year5: "",
              },
              {
                key: '4',
                number: '4.1',
                project: '累计净现金流量(现值)',
                year0: "",
                year1: "",
                year2: "",
                year3: "",
                year4: "",
                year5: "",
              },
              {
                key: '5',
                number: '5',
                project: '现值系数',
                year0: "1.00",
                year1: "0.9091",
                year2: "0.8264",
                year3: "0.7513",
                year4: "0.683",
                year5: "0.6209",
              },
            ],
            Index: [
              {
                key: '6',
                number: '1',
                project: '净现值 NPY',
                value: "",
              },
              {
                key: '7',
                number: '2',
                project: '内部收益率 IRR',
                value: "",
              },
              {
                key: '8',
                number: '3',
                project: '动态投资回收期(年) DPP',
                value: "",
              },
            ],  
            columns_1: [
            {
                title: '序号',
                dataIndex: 'number',
                key: 'number',
              },
              {
                title: '项目/年份',
                dataIndex: 'project',
                key: 'project',
              },
              {
                title: '0',
                dataIndex: 'year0',
                key: '0',
              },
              {
                title: '1',
                dataIndex: 'year1',
                key: '1',
              },
              {
                title: '2',
                dataIndex: 'year2',
                key: '2',
              },
              {
                title: '3',
                dataIndex: 'year3',
                key: '3',
              },
              {
                title: '4',
                dataIndex: 'year4',
                key: '4',
              },
              {
                title: '5',
                dataIndex: 'year5',
                key: '5',
              },
            ],
              columns_2: [
              {
                title: '序号',
                dataIndex: 'number',
                key: 'number',
              },
              {
                title: '指标',
                dataIndex: 'project',
                key: 'project',
              },
              {
                title: '值',
                dataIndex: 'value',
                key: 'value',
              },
            ]
          };
        },
      }
  
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
  .formula{
    text-align:center;
  }
  </style>