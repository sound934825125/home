<template>
<div class="videos" :children="[]">
	<video-player 
		class="video-player vjs-custom-skin"
		ref="videoPlayer"
		:playsinline="true"
		:options="playerOptions"
	>
		<template v-slot="{ player, state }">
		  <div class="custom-player-controls">
		    <button @click="state.playing ? player.pause() : player.play()">
		      {{ state.playing ? 'Pause' : 'Play' }}
		    </button>
		    <button @click="player.muted(!state.muted)">
		      {{ state.muted ? 'UnMute' : 'Mute' }}
		    </button>
		  </div>
		</template>		
	</video-player>
</div>
</template>
<script setup>
	import videoPlayer from '@videojs-player/vue'
	import 'video.js/dist/video-js.css'
	import { defineProps } from 'vue'
	defineProps(['video', 'index'])
	const videos = { 
		playerOptions: {
			autoplay: false,     								// 自动播放
		  muted: true,        								// 静音
		  loop: true,         								// 循环播放
		  preload: 'auto',    								// 加载方式
		  fluid: true,
			sources: [
				{ src: this.video.url, type: 'video/mp4' },
				{ src: '/video/01.mp4', type: 'video/mp4' },
				{}
			],
			poster: "../../static/images/.jpg", // 封面
			width: document.documentElement.clientWidth,
			notSupportedMessage: "此视频暂时无法播放，请稍后再试",
			controlBar: false,     							// 显示控制面板
		},
		playing: true,
		playBtn: '',
	}
</script>
<style scoped>
	.videos {
		position: relative;

		/deep/ .vjs-big-play-button {
			position: absolute;
			width: 80px;
			height: 80px;
			border: none;
			background: transparent;
			left: 40%;
			top: 40%;
			content: none;

			.vjs-icon-placeholder {
				font-size: 100px;
				color: rgba(255, 255, 255, 0.7);
			}
		}

		/deep/ .video-js {
			height: calc(100vh - 50px);
		}
	}
</style>