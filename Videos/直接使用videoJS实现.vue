    <video-js ref="videoPlayer">

<script setup>
  function createVideoJS(){ video.player = videojs(videoPlayer.value, video.options) };
  function destroyVideoJS(){ if (video.player) {video.player.dispose()} };
	onMounted(() => { createVideoJS() });
	onBeforeUnmount(() => { destroyVideoJS() })

	const video = {
		player: null,
		options: {
	    loop: true,         // 循环播放
	    muted: true,        // 静音
			autoplay: true,     // 自动播放
			controls: true,     // 显示控制面板
			// sources: [ { src: '/video/01.mp4', type: 'video/mp4' } ],
			sources: [ ],
	    preload: 'auto',    //  加载方式
	    // inactivityTimeout: number 设置多少毫秒无操作进入不活跃状态
	    userActions: {
	      click: true,      // 开启单击暂停
	      doubleClick: true,// 开启双击全屏
	      // hotkeys        // 自定义热键
	    },
	    // fluid: true,
	    // aspectRatio: "4:3",
	    fill: true,
	    // responsive: true
	    // breakpoints: {}
	    // width: 480
	    // height:
		},
  };
</script>
