<template>
	<!-- 侧边咨询弹窗按钮 -->
	<div class="fixBtn">
		<div class="btn" @mouseover="popupOpacity = 1;popupDisplay ='block'" @mouseout="popupOpacity = 0;popupDisplay ='none'">
			<img src="../assets/img/zixun.png">
			<span>咨询&建议</span>
		</div>
		<div class="popup":style="{opacity : popupOpacity,display : popupDisplay}" @mouseover="popupOpacity = 1;popupDisplay ='block'" @mouseout="popupOpacity = 0;popupDisplay ='none'">
			<div class="popClose"><img src="../assets/img/close.png"></div>
			<ul class="popContent">
				<li>
					<div class="contentIcon">
						<img src="../assets/img/telphone.png">
					</div>
					<div class="contentMain">
						<a>
							<h3>售前咨询</h3>
							<p>95178转1</p>
						</a>
					</div>
				</li>
				<li>
					<div class="contentIcon">
						<img src="../assets/img/kefu.png">
					</div>
					<div class="contentMain">
						<a>
							<h3>云博士 · 智能客服</h3>
							<p>智能诊断，秒级解答</p>
						</a>
					</div>
				</li>
				<li>
					<div class="contentIcon">
						<img src="../assets/img/fankui.png">
					</div>
					<div class="contentMain">
						<a>
							<h3>聆听 · 建议反馈</h3>
							<p>阿里云不是完美的，我们渴望您的建议</p>
						</a>
					</div>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
export default{
	data(){
		return{
			popupOpacity:0,
			popupDisplay:'none',
		}
	},
}
</script>

<style>
.fixBtn{
	position: fixed;
	bottom: 180px;
	right: 15px;
	width: auto;
	z-index: 11;
	.btn{
		width: 44px;
		height: 128px;
		box-shadow: 0 6px 12px 0 rgba(0,0,0,.15);
    background-color: #33cde5;
    text-align: center;
    >img{
    	width: 28px;
  		margin: 8px 0 4px;
    }
    >span{
    	display: inline-block;
	    width: 14px;
	    font-size: 14px;
	    color: #fff;
	    line-height: 17px;
    }
	}
	.popup{
		box-sizing: border-box;
    width: 320px;
    height: 220px;
    padding: 20px;
    background: #fff;
    box-shadow: 0 6px 12px 0 rgba(0,0,0,.15);
    position: absolute;
    top: -91px;
    z-index: 1000;
    right: 52px;
    /* opacity: 0;
    visibility: hidden; */
    transition: all .3s;
    .popClose{
			position: absolute;
	    right: 20px;
	    top: 20px;
	    cursor: pointer;
	    >img{
	    	width: 14px;
	    }
    }
    .popContent{
    	min-height: 24px;
	    padding-left: 0;
	    /* opacity: 0; */
	    transition: all .3s;
	    transition-delay: .1s;
	    >li{
	    	list-style: none;
 				margin-bottom: 20px;
 				display: block;
 				.contentIcon{
 					width: 24px;
			    height: 24px;
			    display: inline-block;
			    vertical-align: middle;
			    img{
			    	width: 100%;
			    }
 				}
 				.contentMain{
 					display: inline-block;
			    vertical-align: middle;
			    margin-left: 12px;
			    >a{
			    	display: block;
				    color: #5f6367;
				    font-size: 14px;
				    >h3{
				    	color: #373d41;
				    	line-height: 24px;
				    }
				    >p{
					    color: #9b9ea0;
					    font-size: 12px;
					    line-height: 24px;
				    }
			    }
 				}
	    }
    }
	}
}
</style>