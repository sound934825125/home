<template><v-app-bar>
  <!-- Search Box -->
  <v-menu open-on-hover>
    <template v-slot:activator="{ props }">
      <v-autocomplete 
       v-bind="props"
       :items="search.items" 
       :menu="false" 
      >
      	<!-- Search Item 搜索列表在被搜索内容存在时显示 -->
        <template v-slot:item="{ props, item, index }"></template>     
      </v-autocomplete>
    </template>
    <!-- Search Referral 搜索推荐在搜索内容为空但获得焦点时显示 -->
    <v-card>
			<v-card-item><v-card-title>{{search.referral.guessYouSearchTitle}}</v-card-title></v-card-item>	 
			<v-card-text><v-row>
				<v-col><v-list>
					<v-list-item v-for="item in search.referral.guessYouSearch"><a href="">{{item.title}}</a></v-list-item>
			</v-list></v-col>
				<v-col><v-list>
					<v-list-item v-for="item in search.referral.guessYouSearch"><a href="">{{item.title}}</a></v-list-item>
			</v-list></v-col>
		</v-row></v-card-text>   	
    </v-card>
    <v-card>
			<v-card-item><v-card-title>{{search.referral.hotSpotTitle}}</v-card-title></v-card-item>	 
			<v-card-text><v-list>
				<v-list-item v-for="item in search.referral.hotSpot"><a href="">{{item.title}}</a></v-list-item>
			</v-list></v-card-text>   	
    </v-card>    
  </v-menu>
  <!-- Btn Group -->
  <v-btn v-for="btn in btnGroup">
    <span>{{btn.text}}</span>
  </v-btn>
  <v-btn variant="flat" color="red-accent-2" class="ml-4 px-8 py-2"><span class="text-white font-weight-bold">登录</span></v-btn>
</v-app-bar></template>
<script setup>
	import { ref, watch } from 'vue'

  const search = {
    placeholder: "热点 | '马鞍' 登录广东沿海 | 做手账的视频 | 盆底肌修复",
    autoUpdate: true,
    model: ['Sandra Adams', 'Britta Holt'],
    search: null,
    name: 'Midnight Crew',
    items: [ {title: "T 4", value: "V 4", props: {prependIcon: 'mdi-home',}} ],
    title: "The summer breeze",

    referral: {
    	guessYouSearchTitle: "猜你想搜",
    	guessYouSearch: [
    		{title: "黄雨萌", ref: ""},
    		{title: "程yooooo", ref: ""},
    		{title: "广播蛋挞王", ref: ""},
    		{title: "童锦程", ref: ""},
    		{title: "黄雨蒙", ref: ""},
    		{title: "百果园", ref: ""},
    	],
    	hotSpotTitle: "抖音热点",
    	hotSpot: [
				{title: "灯火里的中国热气腾腾", ref: "", icon: ""},
				{title: "阿根廷民众烧梅西雕像庆祝新年", ref: "", icon: ""},
				{title: "2023央视春晚第二次联排", ref: "", icon: ""},
				{title: "老年感染者就医全流程", ref: "", icon: ""},
				{title: "演员杜熊文去世", ref: "", icon: ""},
				{title: "姆巴佩蓝网主场观赛", ref: "", icon: ""},
    	]

    }

  };


  const btnGroup = {
    about: {text: "关于抖音"},
    download: {text: "下载抖音"},
    originatorSever: {text: "创作者服务"},
    postVideo: {text: "发布视频"}
  };
</script>
