# vue-video-player

[引用至](https://github.com/surmon-china/videojs-player)

## Usage in Vue

	$ npm install video.js @videojs-player/vue --save

	import VueVideoPlayer from '@videojs-player/vue'
	import 'video.js/dist/video-js.css'
	import { defineComponent } from 'vue'
	export default defineComponent({ components: { VideoPlayer } })	

	app.use(VueVideoPlayer)

	<video-js ref="videoPlayer"/>

**Usage Slot Custom controls elements**

	<video-player :children="[]">
	  <template v-slot="{ player, state }">
	    <div class="custom-player-controls">
	      <button @click="state.playing ? player.pause() : player.play()"> {{ state.playing ? 'Pause' : 'Play' }} </button>
	      <button @click="player.muted(!state.muted)"> {{ state.muted ? 'UnMute' : 'Mute' }} </button>
	    </div>
	  </template>
	</video-player>

## Usage in React

## Component Props

- id
- src
- sources
- width
- height
- preload
- loop
...

## Component Event

**由 Video.js 触发的事件, 参数总是 EventTarget**

- event.loadstart
- event.suspend
- event.abort
- event.error
- event.emptied
...

**由 videojs-player component 触发的事件**

- mounted - { video: HTMLVideoElement, player: VideoJsPlayer, state: VideoPlayerState }
- unmounted
- stateChange - state: VideoPlayerState

## Player State

通过 mounted 或 stateChange 事件获得这个响应的 VideoPlayerState 状态对象。

| Key           | Description          | Value Type                |
|------------------------------------------------------------------|
| src           | 当前播放视频 URL      | String                    |
| currentSrc    | 当前播放视频 URL      | String                    |
| currentSource | 当前播放视频源信息对象 | videojs.Tech.SourceObject |
| width         | Player's width       | Number                    |
| height        | Player's height      | Number                    |
...

## extension 扩展与插件

	import videojs from 'video.js'

	// 初始化插件
	const Plugin = videojs.getPlugin('plugin')
	class ExamplePlugin extends Plugin { /* do something... */ }
	// 注册插件
	videojs.registerPlugin('examplePlugin', ExamplePlugin)
