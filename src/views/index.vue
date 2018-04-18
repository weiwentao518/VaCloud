<template>
	<div class="index">
		<Banner></Banner>
		<!-- 轮播图 -->
		<div class="bannerShow" @mousemove="showMouseMove()">
			<el-carousel trigger="click" height="440px" arrow="never">
	      <el-carousel-item>
	        <div class="showContent">
	        	<h1> 加入云翼计划，让自己脱颖而出 </h1>
	        	<p> 专注大学生成长，一起打造更好的未来 </p>
						<div class="showBtn">查看详情</div>
	        </div>
	        <div class="showImages">
	        	<div class="showRow">
	        		<div class="showImg showImg1">
	        			<img src="../assets/img/show1-1.png">
	        		</div>
	        		<div class="showImg showImg2">
	        			<img src="../assets/img/show1-2.png">
	        		</div>
	        		<div class="showImg showImg3">
	        			<img src="../assets/img/show1-3.png">
	        		</div>
	        	</div>
	        </div>
	      </el-carousel-item>
	      <el-carousel-item>
	        <div class="showContent">
	        	<h1> 聚焦智能制造、企业数字化转型 </h1>
	        	<p> 2017云栖大会 | 苏州峰会 火热报名中 </p>
	      		<div class="showBtn">立即报名</div>
	        </div>
	        <div class="showImages">
	        	<div class="showRow">
	        		<div class="showImg showImg1">
	        			<img src="../assets/img/show2-1.png">
	        		</div>
	        		<div class="showImg showImg2">
	        			<img src="../assets/img/show2-2.png">
	        		</div>
	        		<div class="showImg showImg3">
	        			<img src="../assets/img/show2-3.png">
	        		</div>
	        	</div>
	        </div>
	      </el-carousel-item>
	      <el-carousel-item>
	        <div class="showContent">
	        	<h1> 云数据库Redis单节点集群上线 </h1>
	        	<p> 超凡性价比，满足百万QPS，针对超大型纯缓存业务定制 </p>
	      		<div class="showBtn">查看详情</div>
	        </div>
	        <div class="showImages">
	        	<div class="showRow">
	        		<div class="showImg showImg1">
	        			<img src="../assets/img/show3-1.png">
	        		</div>
	        		<div class="showImg showImg2">
	        			<img src="../assets/img/show3-2.png">
	        		</div>
	        		<div class="showImg showImg3">
	        			<img src="../assets/img/show3-3.png">
	        		</div>
	        	</div>
	        </div>
	      </el-carousel-item>
	      <el-carousel-item>
	        <div class="showContent">
	        	<h1> 竞价型GPU云服务器实例 </h1>
	        	<p> 低至一折起，大幅度降低GPU成本 </p>
	      		<div class="showBtn">查看详情</div>
	        </div>
	        <div class="showImages">
	        	<div class="showRow">
	        		<div class="showImg showImg1">
	        			<img src="../assets/img/show4-1.png">
	        		</div>
	        		<div class="showImg showImg2">
	        			<img src="../assets/img/show4-2.png">
	        		</div>
	        		<div class="showImg showImg3">
	        			<img src="../assets/img/show4-3.png">
	        		</div>
	        	</div>
	        </div>
	      </el-carousel-item>
	      <el-carousel-item>
	        <div class="showContent">
	        	<h1> 云服务器本地SSD型实例 </h1>
	        	<p> 为极致存储性能需求场景而生 </p>
	      		<div class="showBtn">了解详情</div>
	        </div>
	        <div class="showImages">
	        	<div class="showRow">
	        		<div class="showImg showImg1">
	        			<img src="../assets/img/show5-1.png">
	        		</div>
	        		<div class="showImg showImg2">
	        			<img src="../assets/img/show5-2.png">
	        		</div>
	        		<div class="showImg showImg3">
	        			<img src="../assets/img/show5-3.png">
	        		</div>
	        	</div>
	        </div>
	      </el-carousel-item>
	    </el-carousel>
		</div>
		<!-- 尾部 -->
		<div class="bannerFooter">
			<div class="footerModule">
				<ul>
					<li>
						<a>
							<img src="../assets/img/btn1.png">
							<h2>网络增强云服务器</h2>
							<p>450万PPS，稳定降低延迟</p>
						</a>
					</li>
					<li>
						<a>
							<img src="../assets/img/btn2.png">
							<h2>交易所服务</h2>
							<p>完美支撑13亿人口交易量</p>
						</a>
					</li>
					<li>
						<a>
							<img src="../assets/img/btn3.png">
							<h2>复杂美科技牛逼</h2>
							<p>我们公司市值13个亿！！</p>
						</a>
					</li>
					<li>
						<a>
							<img src="../assets/img/btn4.png">
							<h2>行业解决方案</h2>
							<p>深入业务个性化定制</p>
						</a>
					</li>
					<li>
						<a>
							<img src="../assets/img/btn5.png">
							<h2>突发性能云服务器</h2>
							<p>打造最高性价比ECS</p>
						</a>
					</li>
				</ul>
			</div>
		</div>
		<Contact></Contact>
	</div>
</template>

<script>
import Contact from '../components/contact.vue'
import Banner from '../components/banner.vue'

export default{
	data(){
		return{

		}
	},
	components:{
		Contact,
		Banner,
	},
	methods:{
		showMouseMove(){

			let oEvent = window.event;
			//console.log("oEvent: "+oEvent);
			let oShow =document.getElementsByClassName('showRow');
			
			this.showRotateX = oEvent.clientX/100;
			this.showRotateY = oEvent.clientY/100;
			let t = 'rotateX('+this.showRotateX.toFixed(0)+'deg)'+' '+'rotateY('+this.showRotateY.toFixed(0)+'deg)';
			for(let i=0,len=oShow.length;i<len;i++){
				oShow[i].style='transform: '+t+'';
			}
		}
	}
}
</script>

<style>
.index{
	.bannerShow{
		height: 440px;
		background: linear-gradient(#182561, #107099); /* 背景颜色渐变 */
		.showContent{
			color: #fff;
			padding: 90px 0 0 200px;
			height: 100%;    
			>h1{
				text-align: left;
		    font-size: 44px;
		    font-weight: 400;
			}
			>p{
		    text-align: left;
    		font-size: 20px;
			}
			.showBtn{
		    cursor: pointer;
		    text-align: center;
		    line-height: 36px;
		    margin-top: 30px;
		    font-size: 16px!important;
		    float: left;
		    width: 120px;
		    height: 36px;
		    background: transparent;
		    border: 2px solid #fff;
		    transition: 0.2s;
			}
			.showBtn:hover{
	    	background: #fff;
	    	color: #666;
	    }
		}
		.showImages{
			z-index: -1;
	    width: 100%;
	    height: 100%;
	    position: absolute;
	    top: 0;
	    left: 0;
	    right: 0;
	    bottom: 0;
	    transition: all .5s ease-out;
	    .showRow{
	    	transform: rotateX(0deg) rotateY(0deg); 
	    	position: relative;
		    min-width: 1200px;
		    max-width: 1200px;
		    margin-left: auto;
		    margin-right: auto;
		    zoom: 1;
		    transform-style: preserve-3d;
    		transition: all .15s ease-out;
    		.showImg{
					text-align: center;
			    width: 100%;
			    img{
			    	width: 800px;
				    position: absolute;
				    right: -60px;
			    }
    		}
    		.showImg1{
					transform: translateZ(50px);
    		}
    		.showImg2{
					transform: translateZ(100px);
    		}
    		.showImg3{
					transform: translateZ(150px);
    		}
	    }
		}
	}
	.bannerFooter{
    height: 100px;
    width: 100%;
    /* z-index: 100; */
		background: #2784A8;
    /* background-color: hsla(0,0%,100%,.1); */
    .footerModule{
			min-width: 1000px;
			position: relative;
			>ul{
				margin: auto;
		    max-width: 1200px;
		    transition: opacity .3s .6s,visibility 0s .6s,margin-top 0s .6s;
		    >li{
		      width: 20%;
    			float: left;
    			>a{
    				height: 100px;
				    position: relative;
				    display: block;
				    padding: 28px 0 28px 68px;
				    transition: all .3s;
				    border-left: 1px solid #727577;
				    border-color: hsla(0,0%,100%,.06);
				    cursor: pointer;
				    >img{
							position: absolute;
					    left: 20px;
					    top: 34px;
					    width: 32px;
					    filter: grayscale(100%);
				    }
				    h2{
				    	color: #fff;
					    font-weight: bolder;
					    height: 18px;
					    font-size: 16px;
					    margin-bottom: 4px;
				    }
				    p{
				    	color: #fff;
				    	font-size: 14px;
    					line-height: 24px;
				    }
    			}
    			>a:hover{
						background-color: hsla(0,0%,100%,.06);
				    text-decoration: none;
				    border-color: transparent!important;
    			}
		    }
			}
    }
	}
}
</style>