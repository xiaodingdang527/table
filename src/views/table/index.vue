  <template>
  	<div class="table">
  		<el-table :data="tableData" style="width: 100%">
  			<el-table-column prop="date" label="日期" width="180">
  			</el-table-column>
  			<el-table-column prop="name" label="姓名" width="180">
  			</el-table-column>
  			<el-table-column prop="address" label="地址">
  			</el-table-column>
  			<el-table-column>
  				<template slot-scope="scope">
  					<el-button @click="editRow(scope.row)">
  						修改
  					</el-button>
  				</template>
  			</el-table-column>
  			<el-table-column>
  				<template slot-scope="scope">
  					<img :src="scope.row.img" alt="" />
  				</template>
  			</el-table-column>
  		</el-table>
  		<el-dialog title="修改" :visible.sync="dialogVisible" width="600px" :before-close="handleClose">
  			<el-form :model="ruleForm" status-icon ref="ruleForm" label-width="100px" class="demo-ruleForm">
  				<el-form-item label="日期" prop="date">
  					<!-- <el-input type="text" v-model="ruleForm.date" autocomplete="off"></el-input> -->
  					<el-date-picker v-model="ruleForm.date" type="date" placeholder="选择日期时间">
  					</el-date-picker>
  				</el-form-item>
  				<el-form-item label="姓名" prop="name">
  					<el-input type="text" v-model="ruleForm.name" autocomplete="off"></el-input>
  				</el-form-item>
  				<el-form-item label="地址" prop="address">
  					<el-input type="text" v-model="ruleForm.address"></el-input>
  				</el-form-item>
  			</el-form>
  			<span slot="footer" class="dialog-footer">
  				<el-button type="primary" @click="submitForm('ruleForm')">提交</el-button>
  				<el-button @click="resetForm('ruleForm')">重置</el-button>
  			</span>
  		</el-dialog>
  	</div>
  </template>

  <script>
  	export default {
  		data() {
  			return {
  				tableData: [{
  					date: '2016-05-02',
  					name: '王小虎',
  					address: '上海市普陀区金沙江路 1518 弄',
  					img: require('@/assets/logo.png')
  				}, {
  					date: '2016-05-04',
  					name: '王小虎',
  					address: '上海市普陀区金沙江路 1517 弄',

  				}, {
  					date: '2016-05-01',
  					name: '王小虎',
  					address: '上海市普陀区金沙江路 1519 弄'
  				}, {
  					date: '2016-05-03',
  					name: '王小虎',
  					address: '上海市普陀区金沙江路 1516 弄',

  				}],
  				dialogVisible: false,
  				ruleForm: {
  					date: '',
  					name: '',
  					address: ''
  				},
  			}
  		},
  		methods: {
  			editRow(row) {
  				console.log(row)
  				this.dialogVisible = true
  				this.ruleForm = row
  			},
  			//关闭前的回调
  			handleClose(done) {
  				this.$confirm('确认关闭？')
  					.then(_ => {
  						done();
  					})
  					.catch(_ => {});
  			}
  		}
  	}
  </script>

  <style>
  </style>