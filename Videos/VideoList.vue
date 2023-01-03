<template>
	<div class="video-list">
		<swiper :options="swierOptions">
			<swiper-slide v-for="(item, index) in dataList" :key="index">
				<div style="height: 100%; width: 100%; margin: 0 auto">
				<Videos :video="item" ref="videos" :index="index"></Videos>
				</div>
				<div class="info-wrap"><info-bar></info-bar></div>
				<div class="rightbar_wrap"><right-bar @changeCom="showComs"></right-bar></div>
			</swiper-slide>
		</swiper>		
	</div>
</template>
<script setup>
	import Videos from './Videos.vue'
	import { defineProps } from 'vue'
	defineProps(['dataList'])
	const swiper = {
		showComment: false,
		swiperOptions: {
			direction: 'vertical',
			grabCursor: true,
			setWrapperSize: true,
			autoHeight: true,
			slidesPerView: 1,
			mousewheel: true,
			mousewheelControl: true,
			height: window.innerHeight - 50,
			resistanceRatio: 0,
			observePrents: true,
			on: {},
		}
		page: 1,
	}
</script>
<style></style>