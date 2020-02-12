<template>
	<view>
		<pageHeader />
	</view>
</template>

<script>
	import pageHeader from "./pageHeader.vue"
	import interfaces from "../../../utils/interfaces.js"
	export default {
		data(){
			return{
				swiperList:[], 	 //轮播图
				categoryList:[], //分类
				promotion:[]     //活动
			}
		},
		components:{
			pageHeader
		},
		methods:{
			initData(){
				this.request({
				    url: interfaces.getMallData, //仅为示例，并非真实接口地址。
				    success: ((res) =>{
						    console.log(res.data);
							this.swiperList = res.data.swiperList;
							this.categoryList = res.data.categoryList;
							this.promotion = res.data.promotion;
					})
				});
			}
		},
		onLoad() {
			this.initData();
		}
	}
</script>

<style>
</style>
