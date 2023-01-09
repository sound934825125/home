<template>
<div class="module-search">
	<v-autocomplete 
	 v-model:search="autocomplete.search.value"
	 :items="autocomplete.items" 
	 :menu="false" 
	 variant="outlined"
	 density="compact"
	 hide-details
	 placeholder="热点 | '马鞍' 登录广东沿海 | 做手账的视频 | 盆底肌修复"
	>
	  <template v-slot:item="{ props, item, index }"></template>     
	</v-autocomplete>
	<!-- search 为空时推荐 -->
  <v-menu location="bottom" activator="parent" class="referral">
    <v-card>
			<v-card-item><v-card-title>{{referral.guessTitle}}</v-card-title></v-card-item>	 
			<v-card-text><v-row>
				<v-col><v-list :items="referral.guessLeftItems" nav></v-list></v-col>
				<v-col><v-list :items="referral.guessRightItems" nav></v-list></v-col>
			</v-row></v-card-text>   	
			<v-divider></v-divider>
			<v-card-item><v-card-title>{{referral.hotSpotTitle}}</v-card-title></v-card-item>	 
			<v-card-text>
				<v-list class="referral-hotSpotItems" density="compact">
					<v-list-item v-for="item in referral.hotSpotItems" nav height="28" min-height="28">
			      <template v-slot:prepend><v-icon :icon="item.prependIcon" :color="item.prependIconColor"></v-icon></template>
			      <v-list-item-title v-text="item.title"></v-list-item-title>						
					</v-list-item>
				</v-list>
			</v-card-text>	
    </v-card>
  </v-menu>	
</div>
</template>
<script setup>
	import { watch, ref } from "vue"
  const menuModel = ref();
  const autocomplete = {
  	search: ref(),
  	items: [{title: "", value: ""}],
  }
  const referral = {
  	guessTitle: "猜你想搜",
  	guessLeftItems: [
  		{title: "黄雨萌", value: 1, props: {height: "28", minHeight: "28", } },
  		{title: "程yooooo", value: 1, props: {height: "28", minHeight: "28", } },
  		{title: "广播蛋挞王", value: 1, props: {height: "28", minHeight: "28", } },
  	],
  	guessRightItems: [
  		{title: "童锦程", value: 1, props: {height: "28", minHeight: "28", } },
  		{title: "黄雨蒙", value: 1, props: {height: "28", minHeight: "28", } },
  		{title: "百果园", value: 1, props: {height: "28", minHeight: "28", } },
  	],
  	hotSpotTitle: "抖音热点",
  	hotSpotItems: [
			{title: "灯火里的中国热气腾腾", value: 1, prependIcon: "mdi-numeric-1-circle", prependIconColor: "#FFEE58", },
			{title: "阿根廷民众烧梅西雕像庆祝新年", value: 1, prependIcon: "mdi-numeric-2-circle", prependIconColor: "#BDBDBD", },
			{title: "2023央视春晚第二次联排", value: 1, prependIcon: "mdi-numeric-3-circle", prependIconColor: "#8D6E63", },
			{title: "老年感染者就医全流程", value: 1, prependIcon: "mdi-numeric-4", prependIconColor: "", },
			{title: "演员杜熊文去世", value: 1, prependIcon: "mdi-numeric-5", prependIconColor: "", },
			{title: "姆巴佩蓝网主场观赛", value: 1, prependIcon: "mdi-numeric-6", prependIconColor: "", },
  	]
  }
  watch(autocomplete.search, (val) => {
  	if (val !== "") { menuModel.value = false }
  });

</script>
<style lang="sass" scoped>
	.module-search
		min-width: 256px
	.referral
		&-hotSpotItems
			.v-list-item__prepend > .v-icon
				margin-inline-end: 8px
</style>