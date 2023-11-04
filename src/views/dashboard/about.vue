<template>
	<div class="dashboard">
		<div class="zi-left">
		    <div class="left-top">
		        <img src="" alt="">
		        <span>{{ title }}</span>
		    </div>
		    <div class="left-list">
		        <ul>
		            <li>
		                <a href="">首页</a>
		            </li>
		            <li>
		                <a href="">登录</a>
		            </li>
		            <li>
		                <a href="">注册</a>
		            </li>
		            <li>
		                <a href="">退出</a>
		            </li>
		        </ul>
		    </div>
		</div>
		<div class="zi-right">
		    <div class="right-top">
		
		    </div>
		    <div class="right-bottom">
		        <div class="right-section">
		            <ul>
		                <li>
		                    <div>
		                        <h2>201</h2>
		                        <span>机构总数量(家)</span>
		                    </div>
		                    <img src="" alt="">
		                </li>
		                <li></li>
		                <li></li>
		                <li></li>
		            </ul>
		        </div>
		        <div class="right-footer">
		    
		        </div>
		    </div>
		</div>
	</div>
</template>

<script>
	export default{
		data(){
			return{
				title:null
			}
		},
		created(){
			this.title = this.$route.params.title
		}
	}
</script>

<style lang="scss" scoped>
	.dashboard{
		width: 100vw;
		height: 100vh;
		/* position: relative; */
		clear: both;
	}
	.zi-left{
		width: 200px;
		height: 100%;
		/* position: absolute;
		left: 0;
		top: 0; */
		float: left;
		background-color: aquamarine;
	}
	.zi-right{
		width: calc(100% - 200px);
		height: 100%;
		/* position: absolute;
		right: 0;
		top: 0; */
		margin-left: 200px;
		background-color:azure;
	}
	.left-top{
		width: 100%;
		height: 60px;
		background-color: bisque;
		display: flex;
		align-items: center;
		padding: 15px 20px;
		box-sizing: border-box;
	}
	.left-top img{
		width: 30px;
		height: 30px;
		margin-right: 20px;
	}
	.left-list ul{
		padding: 0;
		list-style: none;
	}
	.left-list ul li{
		line-height: 50px;
		padding: 0 20px;
	}
	.left-list ul li a{
		display: block;
		text-decoration: none;
		/* text-indent: 30px; */
		cursor: pointer;
	}
	.left-list ul li :hover{
		opacity:0.5;
	}
	.right-top{
		width: 100%;
		height: 100px;
		background-color: blue;
	}
	.right-bottom{
		padding: 20px;
	}
	.right-section ul{
		display: flex;
	}
	.right-section ul li{
		width: 25%;
		height: 120px;
		display: flex;
		justify-content: space-around;
		align-items: center;
		background-color: red;
		padding: 20px 0;
		box-sizing: border-box;
		border-radius: 12px;
		box-shadow: 8px 8px 8px #ccc;
	}
	.right-section ul li+li{
		margin-left: 20px;
	}
	.right-section ul li div{
		text-align: center;
	}
	.right-section ul li img{
		width: 30px;
		height: 30px;
	}
</style>