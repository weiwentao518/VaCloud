<template>
	<div class="banner">
		<!-- 头部 -->
		<div class="bannerHeader">
			<div class="bannerTop">
				<a href="javascript:;" class="topLogo">
					<img class="soso" src="../assets/img/sousou.gif">
					<img class="logo" src="../assets/img/logo.png">
				</a>
				<div class="topMenu">
					<div class="topMenuLink">
						<a href="javascript:;">控制台</a>
					</div>
					<div class="topMenuLink">
						<a href="javascript:;">备案</a>
					</div>
					<div class="topMenuLink">
						<a href="javascript:;">邮箱</a>
					</div>
					<div class="topMenuLink">
						<a href="javascript:;">登录</a>
					</div>
				</div>
				<div class="topSite" @mouseover="siteOver()" @mouseout="siteOut()">
					<img src="../assets/img/earth.png">
					<span>中国站&nbsp;</span>
					<i v-show="isOver1" class="el-icon-arrow-down"></i>
					<i v-show="isOver2" class="el-icon-arrow-up"></i>
					<ul :class="{siteOver:isOver3}">
						<li class="current"><a href="javascript:;">中国站</a></li>
						<li><a href="javascript:;">International&nbsp;-&nbsp;English</a></li>
						<li><a href="javascript:;">International&nbsp;-&nbsp;简体中文</a></li>
						<li><a href="javascript:;" lang="ja">日本サイト</a></li>
					</ul>
				</div>
				<div class="topSearch">
					<i class="el-icon-search" @click="isClick=!isClick"></i>
					<input type="text" class="searchInput" :class="{activeSearchInput: isClick}" placeholder="【新产品】共享流量包">
				</div>
			</div>
			<div class="bannerDown">
				<div class="downLine">
					<div class="nav" @mouseover="menuOneLeft = 0"  @mouseout="menuOneLeft = -200">
						<img src="../assets/img/nav.png">
						<span>全部导航</span>
					</div>
					<ul class="downMenu">
						<li @mouseover="activeWidth = 88;activeLeft = 0" @mouseout="activeWidth = 0;">
							<a href="javascript:;">最新活动</a>
							<img src="../assets/img/hot.png">
						</li>
						<li @mouseover="activeWidth = 60;activeLeft = 88;downDropType = 0;overDownMenu();"  @mouseout="outDownMenu()">
							<a href="javascript:;">产品</a>
						</li>
						<li @mouseover="activeWidth = 88;activeLeft = 148;downDropType = 1;overDownMenu()"  @mouseout="outDownMenu()">
							<a href="javascript:;">解决方案</a>
						</li>
						<li @mouseover="activeWidth = 100;activeLeft = 236;downDropType = 2;overDownMenu()"  @mouseout="outDownMenu()">
							<a href="javascript:;">数据&nbsp;·&nbsp;智能</a>
						</li>
						<li @mouseover="activeWidth = 60;activeLeft = 336;downDropType = 3;overDownMenu()"  @mouseout="outDownMenu()">
							<a href="javascript:;">安全</a>
						</li>
						<li @mouseover="activeWidth = 74;activeLeft = 396;downDropType = 4;overDownMenu()"  @mouseout="outDownMenu()">
							<a href="javascript:;">云市场</a>
						</li>
						<li @mouseover="activeWidth = 60;activeLeft = 470;downDropType = 5;overDownMenu()"  @mouseout="outDownMenu()">
							<a href="javascript:;">支持</a>
						</li>
						<li @mouseover="activeWidth = 88;activeLeft = 530;"  @mouseout="outDownMenu()">
							<a href="javascript:;">合作伙伴</a>
						</li>
						<div class="line" :style="{width: activeWidth+'px',left: activeLeft+'px'}"></div>
					</ul>
					<a class="registerBtn">免费注册</a>
				</div>
				<!-- 左侧二级菜单 -->
				<div class="allMenu">
					<div class="menuOne" :style="{left: menuOneLeft + 'px'}" @mouseover="menuOneLeft = 0" @mouseout="menuOneLeft = -200">
						<ul>
							<li @mouseover="menuTwoType = 0;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>产品</span>
								<i class="el-icon-arrow-right"></i>
							</li>
							<li @mouseover="menuTwoType = 1;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>解决方案</span>
								<i class="el-icon-arrow-right"></i>
							</li>
							<li @mouseover="menuTwoType = 2;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>云市场</span>
								<i class="el-icon-arrow-right"></i>
							</li>
							<li @mouseover="menuTwoType = 3;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>合作与生态</span>
								<i class="el-icon-arrow-right"></i>
							</li>
							<li @mouseover="menuTwoType = 4;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>云溪社区</span>
								<i class="el-icon-arrow-right"></i>
							</li>
							<li @mouseover="menuTwoType = 5;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>阿里云大学</span>
								<i class="el-icon-arrow-right"></i>
							</li>
							<li @mouseover="menuTwoType = 6;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>创业孵化</span>
								<i class="el-icon-arrow-right"></i>
							</li>
							<li @mouseover="menuTwoType = 7;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>支持</span>
								<i class="el-icon-arrow-right"></i>
							</li>
							<li @mouseover="menuTwoType = 8;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>开发者中心</span>
								<i class="el-icon-arrow-right"></i>
							</li>
							<li @mouseover="menuTwoType = 9;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>了解阿里云</span>
								<i class="el-icon-arrow-right"></i>
							</li>
							<li @mouseover="menuTwoType = 10;menuTwoLeft = 200" @mouseout="menuTwoLeft = -200">
								<span>重要频道</span>
								<i class="el-icon-arrow-right"></i>
							</li>
						</ul>
						<div class="spaceLine"></div>
						<a href="javascript:;">政府通道</a>
						<p>售前咨询 95187 转 1</p>
					</div>
					<div class="menuTwo" :style="{left: menuTwoLeft + 'px'}" @mouseover="menuTwoLeft = 200;menuOneLeft = 0" @mouseout="menuTwoLeft = -200;menuOneLeft = -200">
						<div class="menuTwoLinks" v-if="menuTwoType == 0">
							<ul>
								<li>
									<span>弹性计算</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>存储与CDN</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>数据库</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>网络</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>域名与网站</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>安全</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>分析与搜索</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>云通信</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>应用服务</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>移动云</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>视频服务</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>人工智能</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>大数据</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>物联网</span>
									<i class="el-icon-arrow-right"></i>
								</li>
							</ul>
						</div>
						<div class="menuTwoLinks" v-if="menuTwoType == 1">
							<ul>
								<li>
									<span>行业解决方案</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>通用解决方案</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>安全解决方案</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>大数据解决方案</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>DevOps解决方案</span>
									<i class="el-icon-arrow-right"></i>
								</li>
							</ul>
						</div>
						<div class="menuTwoLinks" v-if="menuTwoType == 2">
							<ul>
								<li>
									<span>基础软件市场</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>网站建设</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>企业应用</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>服务与培训</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>安全市场</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>API市场</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>物联网市场</span>
									<i class="el-icon-arrow-right"></i>
								</li>
							</ul> 
						</div>
						<div class="menuTwoLinks" v-if="menuTwoType == 3">
							<ul>
								<li>
									<span>加入合作伙伴</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>数梦工厂合作</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>蚂蚁金服开放合作</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>公益扶持</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>学生扶持</span>
									<i class="el-icon-arrow-right"></i>
								</li>
							</ul>
						</div>
						<div class="menuTwoLinks" v-if="menuTwoType == 4">
							<ul>
								<h1>博客</h1>
								<li>
									<span>个人博客</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>技术博客</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<div class="spacelines"></div>
								<h1>论坛</h1>
								<li>
									<span>新手上路</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>开发者交流</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<div class="spacelines"></div>
								<h1>问答</h1>
								<li>
									<span>通用技术</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>云产品</span>
									<i class="el-icon-arrow-right"></i>
								</li>
							</ul>
						</div>
						<div class="menuTwoLinks" v-if="menuTwoType == 5">
							<ul>
								<h1>开发者课堂</h1>
								<li>
									<span>云计算课程</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>大数据课程</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>数据库课程</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>通用技术课程</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<div class="spacelines"></div>
								<h1>培训认证</h1>
								<li>
									<span>考试认证</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>客户培训</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<div class="spacelines"></div>
								<h1>人才市场</h1>
								<li>
									<span>云计算企业线上招聘会</span>
									<i class="el-icon-arrow-right"></i>
								</li>
							</ul>
						</div>
						<div class="menuTwoLinks" v-if="menuTwoType == 6">
							<ul>
								<h1>创业孵化平台</h1>
								<li>
									<span>创业孵化-风驰计划</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>园区入驻</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>投资服务</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>企业服务</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<div class="spacelines"></div>
								<h1>创业大学</h1>
								<li>
									<span>资本说</span>
									<i class="el-icon-arrow-right"></i>
								</li>
							</ul>
						</div>
						<div class="menuTwoLinks" v-if="menuTwoType == 7">
							<ul>
								<li>
									<span>帮助文档</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>智能服务</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>支持计划</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>开发者中心</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>建议与反馈</span>
									<i class="el-icon-arrow-right"></i>
								</li>
							</ul>
						</div>
						<div class="menuTwoLinks" v-if="menuTwoType == 8">
							<ul>
								<h1>开发者中心</h1>
								<li>
									<span>开发资源</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>应用开发</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>应用服务</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>SDK</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>DevOps解决方案</span>
									<i class="el-icon-arrow-right"></i>
								</li>
							</ul>
						</div>
						<div class="menuTwoLinks" v-if="menuTwoType == 9">
							<ul>
								<h1>了解阿里云</h1>
								<li>
									<span>关于阿里云</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>分析师报告</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>客户案例</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>基础设施</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>新手学堂</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<div class="spacelines"></div>
								<h1>联系我们</h1>
								<li>
									<span>售前咨询 95187转1</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>联系中国区域商务经理</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<div class="spacelines"></div>
							</ul>
						</div>
						<div class="menuTwoLinks" v-if="menuTwoType == 10">
							<ul>
								<li>
									<span>供应链金融</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>比特元</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>找币</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>BB红包</span>
									<i class="el-icon-arrow-right"></i>
								</li>
								<li>
									<span>复杂美科技</span>
									<i class="el-icon-arrow-right"></i>
								</li>
							</ul>
						</div>
					</div>
				</div>
				<!-- hover下拉菜单 -->
				<div class="downDrop" :style="{height: downDropHeight+'px'}" @mouseover="downDropHeight = 300"  @mouseout="downDropHeight = 0">
					<div class="downDropLinks" v-if="downDropType == 0">
						<div class="categoryRow">
							<h1>弹性计算</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
						<div class="categoryRow">
							<h1>存储与CDN</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
						<div class="categoryRow">
							<h1>数据库</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
						<div class="categoryRow">
							<h1>网络</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
					</div>
					<div class="downDropLinks" v-if="downDropType == 1">
						<div class="categoryRow">
							<h1>行业解决方案</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
						<div class="categoryRow">
							<h1>通用解决方案</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
					</div>
					<div class="downDropLinks" v-if="downDropType == 2">
						<div class="categoryRow">
							<h1>ET大脑</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
						<div class="categoryRow">
							<h1>大数据应用</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
					</div>
					<div class="downDropLinks" v-if="downDropType == 3">
						<div class="categoryRow">
							<h1>安全产品</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
						<div class="categoryRow">
							<h1>安全公益</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
					</div>
					<div class="downDropLinks" v-if="downDropType == 4">
						<div class="categoryRow">
							<h1>网站建设</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
						<div class="categoryRow">
							<h1>企业应用</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
					</div>
					<div class="downDropLinks" v-if="downDropType == 5">
						<div class="categoryRow">
							<h1>帮助与文档</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
						<div class="categoryRow">
							<h1>智能支持</h1>
							<ul>
								<li><a>啦啦啦啦啦</a></li>
							</ul>
						</div>
					</div>
				</div>
			</div>
		</div>
		
		<Contact></Contact>
	</div>
</template>
<script>
import Contact from '../components/contact.vue'

export default{
	data(){
		return{
			isOver1:true,
			isOver2:false,
			isOver3:false,
			isClick:false,
			activeWidth:0,
			activeLeft:0,
			menuOneLeft:-200,
			menuTwoLeft:-200,
			menuTwoType:0,
			downDropHeight:0,
			downDropType:0,
			showRotateX:0,
			showRotateY:0,
			/*showTransform:'rotateX('+showRotateX+'deg)'+' '+'rotateY('+showRotateY+'deg);'*/
		}
	},
	components:{
		Contact,
	},
	methods:{
		siteOver(){
			this.isOver1 = !this.isOver1;
			this.isOver2 = !this.isOver2;
			this.isOver3 = !this.isOver3;
		},
		siteOut(){
			this.isOver1 = !this.isOver1;
			this.isOver2 = !this.isOver2;
			this.isOver3 = !this.isOver3;
		},
		overDownMenu(){
			this.downDropHeight = 300;
		},
		outDownMenu(){
			this.activeWidth = 0;
			this.downDropHeight = 0;
		},
	}
}
</script>
<style scoped>
.banner{
	.bannerHeader{
		transition: 0.4s;
		background-color: #182460;
		.bannerTop{
			height: 2.5rem;
			border-bottom: 1px solid hsla(0,0%,100%,.15);
			.topLogo{
				display: block;
				float: left;
				position: relative;
		    width: 80px;
		    margin-top: 10px;
		    margin-left: 20px;
				.soso{
					width: 100%;
				}
				.logo{
					width: 100%;
					position: absolute;
					left: 0;
					top: 0;
				}
			}
			.topMenu{
				float: right;
				font-size: 14px;
				.topMenuLink{
					float: left;
					height: 2.5rem;
			    line-height: 2.5rem;
			    padding: 0 12px;
			    a{
			    	color: #fff;
			    }
			    a:active ,a:visited, a:hover{
			    	color: #00c1de;
			    }
				}
			}
			.topSite{
				float: right;
		    color: #fff;
		    height: 40px;
		    line-height: 40px;
		    font-size: 14px;
		    position: relative;
		    padding: 0 12px;
		    cursor: pointer;
		    >img{
		    	width:16px;
		    	vertical-align:text-bottom;
		    	margin-right:4px;
		    }
		    &.topSite:hover{
					background-color: #272b2f;
		    }
		    >ul{
		    	display: none;
			    position: absolute;
			    left: 0;
			    top: 40px;
			    background-color: #272b2f;
			    width: 170px;
			    z-index: 999;
			    padding: 10px;
			    cursor: default;
			    >li{
			    	height: 30px;
				    line-height: 30px;
				    cursor: pointer;
						a{
							color: #fff;
							display: block;
	    				height: 100%;
	    				transition: all 0.3s;
						}
						a:active ,a:visited, a:hover{
				    	color: #00c1de;
				    }
			    }
			    .current{
			    	a{
			    		color: #00c1de;
			    		cursor: default;
			    	}
			    }
		    }
		    .siteOver{
		    	display: block;
		    }
			}
			.topSearch{
				margin-top: 6px;
		    height: 30px;
		    line-height: 0;
		    position: relative;
		    padding-left: 40px;
		    float: right;
		    .el-icon-search{
		    	top: 5px;
			    position: absolute;
			    color: #fff;
			    font-size: 18px;
			    display: inline-block;
			    left: 10px;
			    cursor: pointer;
		    }
		    .searchInput{
		    	width: 0;
		    	opacity: 0;
		    	border: 0;
			    background-color: #4f5356;
			    color: #b8bcbf;
			    outline: none;
			    font-size: 14px;
			    height: 28px;
			    padding-left: 10px;
			    transition: width 0.3s;
			    &::-webkit-input-placeholder{
			    	font-size:12px;
			    }
		    }
		    .activeSearchInput{
		    	width: 170px;
		    	opacity: 1;
		    }
			}
		}
		.bannerDown{
			height: 60px;
			border-bottom: 1px solid hsla(0,0%,100%,.15);
			.downLine{
				overflow: hidden;
				font-size: 14px;
				.nav{
					float: left;
			    height: 60px;
			    width: auto;
			    line-height: 60px;
			    padding: 0 20px;
			    color: #fff;
			    cursor: default;
			    text-align: center;
			    >img{
			    	width: 18px;
			    	display: inline-block;
			    	margin-top: -1px;
			    	vertical-align: middle;
			    }
			    >span{
			    	padding-left: 5px;
			    }
			    &.nav:hover{
			    	background: #00c1de;
			    }
				}
				.downMenu{
					float: left;
	    		position: relative;
	    		>li{
	    			float: left;
				    height: 60px;
				    line-height: 60px;
				    padding: 0 16px;
				    position: relative;
				    >a{
				    	display: block;
				    }
				    >a:hover{
				    	color: #00c1de;
				    }
				    >img{
				    	position: absolute;
					    top: 8px;
					    right: 4px;
					    width: 24px;
				    }
	    		}
	    		.line{
	    			position: absolute;
				    height: 3px;
				    bottom: 0;
				    background: #00c1de;
	    			width: 0px;
	    			left: 0px;
	    			transition: all 0.2s cubic-bezier(.4,0,.2,1);
	    		}
				}
				.registerBtn{
					float: right;
			    height: 60px;
			    line-height: 60px;
			    background: #00c1de;
			    padding: 0 32px;
			    cursor: pointer;
			    &.registerBtn:hover{
			    	background-color: #28d0e9;
			    }
				}
			}
			.allMenu{
				width: 200px;
				.menuOne{
					background-color: #272b2e;
					width: 200px;
					height: calc(100%-100px);
					box-sizing: border-box;
					border-right: 1px solid hsla(0,0%,100%,.15);
			    padding: 20px 0;
			    position: absolute;
			    /* display: none; */
			    overflow: hidden;
			    transition: 0.3s;
			    z-index: 9;
			    >ul{
				   	margin-bottom: 20px;
			    	font-size: 14px;
			    	width: 100%;
			    	>li{
			    		display: block;
					    height: 24px;
					    line-height: 24px;
					    font-size: 14px;
					    padding: 16px 20px;
					    cursor: pointer;
			    		color: #fff;
			    		width: 100%;
			    		.el-icon-arrow-right{
								float: right;
								margin-top: 5px;
			    		}
			    	}
			    	>li:hover{
		    			color: #00c1de;
		    		}
		    		>li:first-child{
				    	padding-top: 0;
				    }
			    }
			    .spaceLine{
						margin: 12px 20px;
				    height: 1px;
				    opacity: 0.5;
				    background: #fff;
			    }
			    >a{
			    	font-size: 14px;
			    	height: 18px;
				    line-height: 18px;
				    padding-top: 10px;
				    padding-left: 20px;
			    }
			    >p{
			    	position: absolute;
				    bottom: 10px;
				    left: 0;
				    right: 0;
				    height: 18px;
				    line-height: 18px;
				    padding-top: 10px;
				    padding-left: 20px;
				    padding-bottom: 20px;
				    font-size: 14px;
				    color: #fff;
				    background: #272b2e;
			    }
				}
				.menuTwo{
					background: #272b2e;
	    		width: 200px;
	    		height: calc(100%-100px);
	    		padding: 20px 0;
			    box-sizing: border-box;
			    position: absolute;
			    /* left: 0px;
			    display: none; */
			    overflow: hidden;
			    transition: 0.3s;
			    z-index: 8;
			    .menuTwoLinks{
			    	margin-bottom: 20px;
			    	font-size: 14px;
	    			height: 100%;
	    			>ul{
	    				width: 200px;
	    				h1{
	    					height: 24px;
						    line-height: 24px;
						    font-size: 18px;
						    padding:0 20px;
						    color: #fff;
	    				}
	    				>li{
	    					display: block;
						    height: 24px;
						    line-height: 24px;
						    font-size: 14px;
						    padding: 16px 20px;
						    color: #fff;
						    cursor: pointer;
						    .el-icon-arrow-right{
						    	float: right;
									margin-top: 5px;
						    }
	    				}
	    				>li:hover{
			    			color: #00c1de;
			    		}
			    		>li:first-child{
					    	padding-top: 0;
					    }
					    .spacelines{
								margin: 12px 20px;
						    height: 1px;
						    opacity: 0.5;
						    background: #fff;
					    }
	    			}
			    }
				}
			}
			.downDrop{
	    	text-align: center;
	    	transition: height .2s cubic-bezier(0,0,.2,1) 0ms;
		    height: 300px;
		    overflow: hidden;
		    background: #272b2e;
		    color: #fff;
		    position: relative;
		    z-index: 10;
		    box-shadow: 0 2px 6px 0 rgba(0,0,0,.3);
		    padding-left: 120px;
		    .downDropLinks{
		    	padding: 28px 20px;
					.categoryRow{
						float: left;
				    width: 180px;
				    margin-right: 16px;
				    >h1{
					    font-size: 14px;
					    font-weight: 600;
					    height: 24px;
					    line-height: 24px;
					    margin-bottom: 12px;
				    }
				    >ul{
				    	>li{
								font-size: 12px;
						    line-height: 24px;
						    margin-bottom: 4px;
						    >a{
						    	color: #c3c5c6;
						    	cursor: pointer;
						    }
						   	a:hover{
						   		color: #00c1de;
						   	}
				    	}
				    }
					}
		    }
			}
		}
		&.bannerHeader:hover{
			background-color: #373D41;
		}
	}
}
</style>