<template>
  <div class="hello" >
    <el-container >
      <el-aside width="250px" >
        <el-col :span="24">
          <div class="asidetitle">
            <img src="../assets/title.png" alt="" width="100%" height="50%">
            <span text-color="#fff">上海正也药业有限公司</span>
          </div>
          <el-menu default-active="2" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose"
            background-color="#2a3139" text-color="#fff" active-text-color="#ffd04b">
            <el-submenu index="1">
              <template slot="title">
                <i class="el-icon-document"></i>
                <span>功能功能功能A</span>
              </template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-submenu>
            <el-submenu index="2">
              <template slot="title">
                <i class="el-icon-suitcase-1"></i>
                <span slot="title">功能B</span>
              </template>
              <el-menu-item index="2-1">选项1</el-menu-item>
            </el-submenu>
            <el-menu-item index="3">
              <i class="el-icon-document"></i>
              <span slot="title">功能功能C</span>
            </el-menu-item>
            <el-menu-item index="4">
              <i class="el-icon-setting"></i>
              <span slot="title">功能功能D</span>
            </el-menu-item>
          </el-menu>
        </el-col>
      </el-aside>
      <el-container>
        <el-header class="headbox">
          <div class="btn">
            <img src="../assets/home.png" alt="">
            首页
          </div>
          <div class="btn">
            <img src="../assets/shuju.png" alt="">
            主数据
          </div>
          <div class="btn">
            <img src="../assets/guanli.png" alt="">
            辖区管理
          </div>
          <div class="btn">
            <img src="../assets/fx.png" alt="">
            
          </div>
        </el-header>
        <div class="minheard">
          <el-breadcrumb separator="/">
            <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
            <el-breadcrumb-item><a href="/">活动管理</a></el-breadcrumb-item>
            <el-breadcrumb-item>活动列表</el-breadcrumb-item>
            <el-breadcrumb-item>活动详情</el-breadcrumb-item>
          </el-breadcrumb>
          <div class="crumb">新增二级商议协议</div>
        </div>
        <el-main>
          <div>
            <div class="line">
            </div>
            <span class="lineindex" border-radius="50%">1</span>
            <span  class="lineindex1">协议主题</span>
            <div class="line"></div>
          </div>
          
          <div class="maintwo">
            <el-form ref="form" :model="form" :rules="rules" label-width="80px" :inline="false">
            <!-- <el-form-item label="活动名称" prop="name">
              <el-input v-model="form.name"></el-input>
            </el-form-item> -->
            <el-row>
              <el-col :span="12">
                <el-row>
                  <el-col :span="9">
                    <el-form-item label="协议客户" prop="region">
                      <el-select v-model="form.region" placeholder="请选择客户">
                        <el-option label="区域一" value="shanghai"></el-option>
                        <el-option label="区域二" value="beijing"></el-option>
                      </el-select>
                      <!-- <span class="tle">上海正也药业有限公司</span> -->
                    </el-form-item>
                  </el-col>
                  <el-col :span="12">
                    <el-form-item label="上海正也药业有限公司" prop="name" label-width="230px">
                    </el-form-item>
                  </el-col>
                </el-row>
              </el-col>
              <el-col :span="12">
                <el-form-item label="协议状态" prop="region">
                  <el-select v-model="form.region" placeholder="">
                    <el-option label="正常" value="正常"></el-option>
                    <el-option label="不正常" value="不正常"></el-option>
                  </el-select>
                </el-form-item>
              </el-col>
            </el-row>
            <el-row>
              <el-col :span="12">
                <el-row>
                  <el-col :span="9">
                    <el-form-item label="购进指标" prop="region">
                      <el-select v-model="form.region" placeholder="请选择活动区域">
                        <el-option label="金额" value="1"></el-option>
                        <el-option label="数量" value="2"></el-option>
                      </el-select>
                    </el-form-item>
                  </el-col>
                  <el-col :span="12">
                    <el-form-item label="" prop="name" style="width: 80%;">
                      <el-input v-model="form.name" placeholder="输入金额/数量"></el-input>
                    </el-form-item>
                  </el-col>
                </el-row>
              </el-col>
              <el-col :span="12">
                <el-row>
                  <el-col :span="9">
                    <el-form-item label="纯销指标" prop="region">
                      <el-select v-model="form.region" placeholder="">
                        <el-option label="金额" value="1"></el-option>
                        <el-option label="数量" value="2"></el-option>
                      </el-select>
                    </el-form-item>
                  </el-col>
                  <el-col :span="12">
                    <el-form-item label="" prop="name" style="width: 80%;">
                      <el-input v-model="form.name" placeholder="输入金额/数量"></el-input>
                    </el-form-item>
                  </el-col>
                </el-row>
              </el-col>
            </el-row>
            <el-row>
              <el-col :span="12">
                <el-row>
                  <el-col :span="9">
                    <el-form-item label="销售渠道" prop="region">
                      <el-select v-model="form.region" placeholder="请选择区域">
                        <el-option label="金额" value="1"></el-option>
                        <el-option label="数量" value="2"></el-option>
                      </el-select>
                    </el-form-item>
                  </el-col>
                  <el-col :span="3">
                    <el-form-item label="" prop="region">
                      <el-tag closable>全国</el-tag>
                    </el-form-item>
                  </el-col>
                </el-row>
              </el-col>
              <el-col :span="12">
                <el-form-item label="签订时间" prop="date">
                  <el-date-picker type="date" placeholder="选择日期" v-model="form.date1"
                    style="width: 86%;"></el-date-picker>
                </el-form-item>
              </el-col>
            </el-row>
            <el-row>
              <el-col :span="12">
                <el-row>
                  <el-col :span="9">
                    <el-form-item label="购进渠道" prop="region">
                      <el-select v-model="form.region1" placeholder="请指定渠道">
                        <el-option label="金额" value="1"></el-option>
                        <el-option label="数量" value="2"></el-option>
                      </el-select>
                    </el-form-item>
                  </el-col>
                  <el-col :span="8">
                    <el-form-item label="" prop="region">
                      <el-select v-model="form.region" placeholder="请选择渠道">
                        <el-option label="金额" value="1"></el-option>
                        <el-option label="数量" value="2"></el-option>
                      </el-select>
                    </el-form-item>
                  </el-col>
                </el-row>
              </el-col>
            </el-row>
          </el-form>
          </div>
          <div class="maintwo">
            <el-table :data="tableData"  style="width: 100%" :header-cell-style="{'text-align':'center'}" >
            <el-table-column prop="date" label="指定渠道编码" align="center" width="480">
            </el-table-column>
            <el-table-column prop="name" label="指定渠道名称" align="center" width="480">
            </el-table-column>
            <el-table-column prop="address" label="所在省" align="center" width="480">
            </el-table-column>
          </el-table>
          </div>
          
          <div >
            <div class="line">
            </div>
            <span class="lineindex">2</span>
            <span class="lineindex1">产品政策</span>
            <div class="line"></div>
          </div>
         <div class="maintwo" > 
          <el-row :gutter="24">
            <el-col :span="3">
              <el-button type="primary" size="mini">添加产品</el-button>
            </el-col>
            <el-col :span="5">
              <span class="pice">购进指标(万元) :</span>
              <span class="pice1">￥152.65</span>
            </el-col>
            <el-col :span="10">
              <span class="pice">指标按季度分解(万元) :</span>
              <span class="pice1">[Q1]￥12.5, </span>
              <span class="pice1">[Q2]￥12.5, </span>
              <span class="pice1">[Q3]￥12.5, </span>
              <span class="pice1">[Q4]￥12.5, </span>
            </el-col>
            <el-col :span="5">
              <span class="pice">纯销总指标(万元) :</span>
              <span class="pice1">￥152.65</span>
            </el-col>
          </el-row>
          

         </div  >
         <div>
          <div class="maintwo">
            产品:
            <el-select v-model="value" placeholder="请选择产品" size="mini">   
            </el-select>
            <span  :style="{color:'#66b1ff',marginLeft:'20px',marginRight:'40px'}">美复胶丸  24粒/盒</span>
           协议效期:
            <el-date-picker
              size="mini"
              v-model="value1"
              type="daterange"
              range-separator="至"
              start-placeholder="开始日期"
              end-placeholder="结束日期">
            </el-date-picker>
          </div>
        
            <div class="tablebox">
              <el-table
              :data="Data"
              style="width: 100%">
              
              <el-table-column
                prop="date"
                label="协议价(元)"
               >
              <el-input v-model="input"   placeholder="请选择输入"></el-input>

              </el-table-column>
              <el-table-column
                prop="name"
                label="票价(元)"
                >
                <el-input v-model="input"  placeholder="请选择输入" ></el-input>
              </el-table-column>
              <el-table-column
                prop="address"
                label="购进指标量(大单位)">
                <el-input v-model="input"  placeholder="请选择输入"></el-input>
              </el-table-column>
              <el-table-column
                prop="address"
                label="购进指量(小单位)">
                <el-input v-model="input" placeholder="请选择输入" ></el-input>
              </el-table-column>
              <el-table-column
                prop="address"
                label="购进金额(万)">
                <el-input v-model="input" placeholder="请选择输入" ></el-input>
              </el-table-column>
              <el-table-column
                prop="address"
                label="纯销指标量(小单位)">
                <el-input v-model="input"  placeholder="请选择输入"></el-input>
              </el-table-column>
              <el-table-column
                prop="address"
                label="纯销指金额万元)">
                <el-input v-model="input" placeholder="请选择输入" ></el-input>
              </el-table-column>
              </el-table>
            </div>
            <div class="tablebox">
              <el-table
              :data="Data1"
              style="width: 100%">
              
              <el-table-column
                prop="date"
                label="分销奖励"
               >
              <el-input v-model="input"   placeholder="请选择输入"></el-input>

              </el-table-column>
              <el-table-column
                prop="name"
                label="费用科目"
                >
                <el-select v-model="value" placeholder="单选项1">
                  <el-option
                    label="单选项1"
                    :value="1">
                  </el-option>
                </el-select>
              </el-table-column>
              <el-table-column
                prop="address"
                label="零售配送">
                <el-input v-model="input"  placeholder="请选择输入"></el-input>
              </el-table-column>
              <el-table-column
                prop="address"
                label="费用科目">
                <el-select v-model="value" placeholder="单选项1">
                  <el-option
                    label="单选项1"
                    :value="1">
                  </el-option>
                </el-select>
              </el-table-column>
              <el-table-column
                prop="address"
                label="医疗配送商">
                <el-input v-model="input" placeholder="请选择输入" ></el-input>
              </el-table-column>
              <el-table-column
                prop="address"
                label="费用科目">
                <el-select v-model="value" placeholder="单选项1">
                  <el-option
                    label="单选项1"
                    :value="1">
                  </el-option>
                </el-select>
              </el-table-column>
              <el-table-column
                prop="address"
                label="自定义7">
                <el-date-picker
                  v-model="value1"
                  type="date"
                  placeholder="选择日期">
                </el-date-picker>
              </el-table-column>
              <el-table-column
                prop="address"
                label="自定义8">
                <el-date-picker
                  v-model="value1"
                  type="date"
                  placeholder="选择日期">
                </el-date-picker>
              </el-table-column>
            </el-table>
            </div>
         </div>
         <div  >
            <div class="line">
            </div> 
            <span class="lineindex">3</span>
            <span class="lineindex1">补充协议</span>
            <div class="line"></div>
          </div>
         <div  class="maintwo" >
          <el-button  :style="{float: 'right'} " type="primary" size="mini">新增</el-button>
          <el-tabs v-model="activeName" type="card" @tab-click="handleClick">
            <el-tab-pane label="补充协议1" name="first"></el-tab-pane>
            <el-tab-pane label="补充协议2" name="second"></el-tab-pane>
            <el-tab-pane label="补充协议3" name="third"></el-tab-pane>
            <div >
              <el-row > 
                <el-col :span="23">协议内容</el-col>
                <el-col :span="1"><el-button size="mini" type="warning">删除</el-button></el-col>
              </el-row>
              <el-input 
                type="textarea"
                :rows="2"
                placeholder="请输入内容"
                v-model="textarea">
              </el-input>
            </div>
          </el-tabs>
         </div>
         <div  class="maintwo">
          <el-button  type="primary" size="mini">保存</el-button>
         </div>

        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      },
      tableData: [{
        date: 'BJ000090',
        name: '宁波九州通药业有限公司',
        address: '浙江省'
      }, {
        date: 'BJ000192',
        name: '国药控股精华有限公司',
        address: '浙江省'
      }, {
        date: 'BJ000283',
        name: '老百姓药业有限公司',
        address: '浙江省'
      },],
      Data: [{
        date: 'BJ000090',
        name: '宁波九州通药业有限公司',
        address: '浙江省'
      }],
      Data1: [ {
        date: 'BJ000283',
        name: '老百姓药业有限公司',
        address: '浙江省'
        }],
      value:'',
      value1:'',
      activeName:'first',
      input:'',
      textarea:'',
      rules: {
        name: [
          { required: true, message: '请输入', trigger: 'blur' },
          { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
        ],
        region: [
          { required: true, message: '请选择', trigger: 'change' }
        ],
        date1: [
          { type: 'date', required: true, message: '请选择日期', trigger: 'change' }
        ],
        date2: [
          { type: 'date', required: true, message: '请选择时间', trigger: 'change' }
        ],
        type: [
          { type: 'array', required: true, message: '请至少选择一个活动性质', trigger: 'change' }
        ],
        resource: [
          { required: true, message: '请选择活动资源', trigger: 'change' }
        ],
        desc: [
          { required: true, message: '请填写活动形式', trigger: 'blur' }
        ]
      }
    }
  },
  methods: { 
    handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClick(tab, event) {
        console.log(tab, event);
      }
  }
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
} */
.el-header,
.el-footer {
  background-color: #2a3139;
  color: #333;
  text-align: center;
}

.el-aside {
  background-color: #2a3139;
  color: #333;
  text-align: left;
  height: 1570px;
}
.asidetitle {
  height: 60px;
  background-color: #2a3139;
  color: #fff;
  text-align: left;
  font-size: 14px;
  margin-left: 20px;
}
.el-main {
  background-color: #E9EEF3;
  color: #fff;
  text-align: left;
}
.minheard {
  width: 100%;
  text-align: left;
  padding: 20px;
  border-bottom: 1px solid #2a3139;
}

.minheard>span {
  font-size: 20px;
}
.crumb{
  margin-top: 10px;
  font-size: 20px;
}
.line {
  display: inline-block;
  width: 45%;
  border: 1px dashed #ccc;
}
.lineindex {
  display: inline-block;
  height: 20px;
  width: 20px;
  text-align: center;
  border-radius: 10px;
  background-color: blue;
}
.lineindex1{
  font-size: 18px;
  color: #000;
}
.pice{
  font-size: 14px;
  color: #000;
}
.pice1{
  margin-left: 5px;
  font-size: 16px;
  font-weight: 700;
  color: #000;
}
.maintwo{
  margin-top: 10px;
  padding: 20px;
  background-color: #fff;
  color: #000;
}
.tablebox{
  margin-top:20px;
  border :1px solid #eee
}
.headbox{
  color: #ccc;
display: flex;

}
.btn{
height: 60px;
width: 150px;
line-height: 60px;
font-size: 20px;
text-align: center;
}
.btn img{
  vertical-align: middle;
}
.tle{
  font-size: 20px;
  color: #333;
}
body>.el-container {
  margin-bottom: 40px;
}

.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
}

.el-container:nth-child(7) .el-aside {
  line-height: 320px;
}
</style>

